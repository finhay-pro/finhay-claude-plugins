---
name: document-legacy-service
description: Use when the user wants to document, reverse-engineer, or understand a legacy service, product, or codebase that has little or no existing documentation. Also use when user asks to create a Product Card, generate business logic docs, or says things like "no one knows how this works", "document this service", "what does this codebase do", or "create docs for this project". This skill is especially relevant for services with database access via Metabase MCP.
---

# Document Legacy Service

## Overview

Reverse-engineer business logic from a running service's source code, database, and existing docs — then produce structured documentation with explicit confidence levels.

**Core principle: Never assume silently. Precision over completeness.** Every claim must be traceable to evidence (code, real data, or human confirmation). When you can't verify something, say so — a gap marked ❓ is more valuable than a wrong answer presented as fact.

This matters because these docs describe **running production services**. Someone will use them to debug incidents, onboard new engineers, or make operational decisions. Wrong assumptions in docs are worse than gaps.

## When to Use

- User wants to document a service/product with no or outdated documentation
- User asks to reverse-engineer business logic from code
- User wants to create a Product Card on Confluence
- User says things like "no one knows how this works" or "document this codebase"

## Setup — Verify Prerequisites, Then Ask

Before any documentation work, verify the environment is ready and gather inputs from the user.

### Step 1: Verify prerequisites (do this silently, don't ask the user)

**Codebase check:**
- Confirm the current working directory looks like the right project. Check for key indicators: `build.gradle`/`pom.xml`/`package.json`, `src/` directory, a `README`, or `.git`.
- If the directory looks wrong (e.g., empty, or a different project), stop and tell the user: "The current directory is `[path]` — is this the service you want to document? If not, please `cd` to the right directory first."

**Metabase MCP check:**
- Try a simple query like listing databases or `SELECT 1` to verify Metabase MCP is connected and responsive.
- If it fails: tell the user step-by-step how to set it up:
  1. "Metabase MCP is not connected. To set it up, run:"
  2. `claude mcp add metabase-mcp -e METABASE_URL=<your-url> -e METABASE_API_KEY=<your-key> -- npx -y @jerichosequitin/metabase-mcp`
  3. "Then restart this session."
- If it works but user doesn't know the database ID: list all databases and ask them to pick the right one.

**Confluence MCP check (only if user wants Confluence output):**
- Try a simple search to verify `mcp-atlassian` is connected.
- If it fails: tell the user step-by-step how to set it up, or skip Confluence output and proceed with local markdown only.

### Step 2: Ask the user

Once prerequisites are verified, ask these questions:

1. **Database ID**: "Metabase is connected. Here are the available databases: [list]. Which one is this service's database?"
2. **Confluence**: "Do you want me to create a Product Card on Confluence too, or just local markdown docs? If Confluence, share the link or page ID of the parent page."
3. **Existing docs**: "Is there any existing documentation I should check first? Confluence page links, wiki, README?"

Store the answers — they determine which phases are possible. If Metabase is not available, proceed without it but note that confidence levels will be mostly ⚠️ (inferred from code only).

## Confidence Level System

Every factual claim in the output docs MUST carry a confidence marker:

| Marker | Level | Meaning | Evidence required |
|--------|-------|---------|-------------------|
| ✅ | **Verified** | Cross-checked code + real data, or human confirmed | Metabase query result, log evidence, or user confirmation |
| ⚠️ | **Inferred** | Derived from code analysis only | Source code reference (file:line) |
| ❓ | **Unknown** | Multiple possibilities, can't determine from available evidence | List what's ambiguous and why |

**Default confidence is ⚠️, not ✅.** You must actively verify to upgrade to ✅.

### What triggers each level

**✅ Verified — requires at least one of:**
- Metabase query confirms the data matches code expectations
- User explicitly confirms ("yes, that's correct")
- Cross-reference between 2+ independent sources (code + Confluence + data all agree)

**⚠️ Inferred — when:**
- You read it in code but haven't checked real data
- Code has multiple versions/paths and you don't know which is active
- Config values from properties files that might be overridden at deploy

**❓ Unknown — when:**
- Multiple code paths exist and you can't determine which runs in production (e.g., 5 versions of the same endpoint)
- Schedule times, cron configs, or external triggers not in the repo
- Values that depend on infrastructure config outside the codebase
- Anything you'd need production logs or human knowledge to determine

## Red Flags — Things You Must NOT Do

These are the most common failure modes when documenting legacy services. Each one was observed in baseline testing:

| Failure | Example | What to do instead |
|---------|---------|-------------------|
| **Guess which version is "current"** | "v4 is the latest, so it must be the one used" | List ALL versions (see below), mark ❓, ask user to verify via logs |
| **Invent schedule times** | "Runs at 0:30 every night" | Mark ❓ — schedule config is rarely in the repo |
| **Present inferred info as verified** | "The EOD job processes..." (no marker) | Always add ⚠️ unless you verified with data |
| **Pick one interpretation when code is ambiguous** | "This field means X" when it could mean X or Y | List both interpretations, mark ❓ |
| **Fill in placeholder values** | "Owner: Engineering Team" | Write "[Cần cập nhật]" or "[Needs input]" |
| **Assume prod config = properties file** | "Redis host is 10.0.0.28" | Note "from application.properties ⚠️ — may be overridden by env vars" |
| **List only some versions** | Showing 2 of 6 EOD endpoints because they "look most relevant" | List EVERY version found in code — the user needs the full picture to identify the right one |
| **Guess what acronyms stand for** | "TVS = Tan Viet Securities" when it's actually "Thiên Việt Securities" | If the full name isn't explicitly in code or docs, mark ❓ and ask the user. Never fabricate expansions of acronyms — you will get them wrong and the mistake will propagate through all docs and Confluence pages. |
| **Include docs from a different service** | Including a postmortem from "vnsc-stock-trading" in docs for "finhay-stock-trading" because both contain "stock trading" | Every Confluence page must be verified against the exact repo/service name before inclusion (see Service Disambiguation below) |

### Multiple Versions Rule

When you find multiple versions of the same functionality (e.g., v1/v2/v3/v4 of an endpoint, or multiple implementations of a service), you MUST:

1. **List ALL of them** in a single table — don't filter to "the ones that look active"
2. **Note which are commented out** vs active in code
3. **Note differences** between versions (retry logic, batch size, different commands)
4. **Mark ❓ which one production actually uses** — unless you can verify via logs or user confirmation

The reason this matters: in legacy codebases, the "latest" version is often NOT the one running in production. Old versions get kept around "just in case" and the scheduler/cron config lives outside the repo. Filtering versions based on your judgment hides information the user needs.

**Example — what to write:**
```
| Path | Command | Notes | Status |
|------|---------|-------|--------|
| PUT /endpoint/v1 | CommandV1 | Original, no retry | Active in code |
| PUT /endpoint/v2 | CommandV2 | Per-item processing | Active in code |
| PUT /endpoint/v3 | CommandV3 | Retry loop + alerts | Active in code |
| PUT /endpoint/v4 | CommandV4 | Batch processing | Active in code |

❓ Which version is called in production is unknown — scheduler config is external.
```

## Process — Three Phases

### Phase 1: Discovery (parallel)

Launch 4+ agents in parallel to analyze the codebase. Simultaneously query Metabase for real data.

**Agent tasks:**

1. **Entity & Data Model agent**: Read all model/entity classes. Extract table names, fields, relationships, enums, status values.

2. **API & Controller agent**: Read all controllers/routes. Extract endpoints, methods, request/response types, which service each calls.

3. **Business Logic agent**: Read services, commands, event handlers. Extract state machines, business rules, event flows, formulas.

4. **Core Flow Deep-Dive agent**: Identify the 2-3 most critical business flows and trace them end-to-end through the actual code. For each flow, document: (a) the exact sequence of method calls, (b) what happens to the user's data/money/assets at each step, (c) what happens when the flow succeeds, and (d) what happens when it fails or partially completes. This agent answers the question a new engineer would ask first: "what's the one thing I MUST understand about this system?"

    The reason this exists as a separate agent: the Business Logic agent tends to describe the system's *structure* (which services exist, what they do) but misses the system's *behavior* (how data actually flows through those services step by step, and what happens at each decision point). Structure without behavior leaves the reader knowing what the pieces are but not how they fit together.

    How to identify the critical flows: look for the operation that touches the most tables, involves the most services, or has the most status transitions. In a trading system it's order matching and settlement. In a payments system it's the payment lifecycle. In a savings product it's the deposit/interest/withdrawal cycle.

**Metabase queries (if available):**
- `SHOW TABLES` or equivalent — compare with code entities
- For each key table: `SELECT status/type/state, COUNT(*) GROUP BY` — reveals actual states vs what code defines
- Row counts and date ranges — reveals scale and activity
- Any data anomalies (stuck records, unexpected statuses)

**Confluence search (if available):**
- Search for the service name
- Read any existing pages — extract business context, Figma links, runbook procedures
- Note: Confluence docs may be outdated. Always cross-reference claims against code.
- **Service disambiguation (critical):** See the section below.

#### Service Disambiguation — Avoiding Cross-Contamination

This step exists because of a real incident: when documenting `finhay-stock-trading`, Confluence search returned pages from `vnsc-stock-trading` (a completely different service) because both contained "stock trading" in their names. An incident report from the wrong service was included in the final docs. This is a serious error — it puts wrong information in production documentation.

**Before using any Confluence page, verify service ownership:**

1. **Identify the exact repo/service name** from the codebase (e.g., from `settings.gradle`, `package.json`, `Dockerfile`, or git remote URL).
2. **When searching Confluence**, note that multiple services often share keywords. A search for "stock trading" may return results for `finhay-stock-trading`, `vnsc-stock-trading`, `stock-price-service`, etc.
3. **For each Confluence page found**, check if it mentions the exact service/repo name — not just shared keywords. Look for:
   - GitHub repo links (e.g., `github.com/finhay/stock-trading` vs `github.com/finhay-pro/vnsc-stock-trading`)
   - Service names in deployment/golive pages
   - Database names that match the service
4. **Build a disambiguation table** early in the process:
   ```
   | Service | Repo | Database | Notes |
   |---------|------|----------|-------|
   | finhay-stock-trading | finhay/stock-trading | finhaydb_stock_trading | THIS service (documenting) |
   | vnsc-stock-trading | finhay-pro/vnsc-stock-trading | vnsc_trading_api | DIFFERENT service — exclude |
   | stock-price-service | finhay/stock-price-service | — | Related but separate |
   ```
5. **When in doubt, exclude the page** and note it as ❓ rather than including content from the wrong service.

**Output of Phase 1:** Raw findings from all sources, not yet synthesized.

### Phase 2: Cross-Reference & Verify

This is where precision matters most. Compare findings across sources:

1. **Code entities vs actual DB tables** — Are there tables in the DB not in code? Entities in code not in DB? (backup tables, temp tables, migration artifacts)

2. **Enum values in code vs actual data** — Does code define statuses that never appear in real data? Does real data contain values not in code enums?

3. **Confluence claims vs code** — Does the spec match the implementation? If Confluence says "min 100M" but code says `200_000L`, which is correct? (Answer: check both and report the discrepancy, let human resolve)

4. **Multiple code paths** — When multiple versions of an endpoint/job exist, do NOT pick one. List all and mark ❓ unless you can verify which is active.

5. **Config values** — Note which environment they come from (dev vs prod properties). Prod values may differ from what's in the repo if overridden by env vars or secrets manager.

**Output of Phase 2:** Verified findings (✅), inferred findings (⚠️), and a list of unknowns (❓).

### Phase 3: Generate Documentation

Produce documentation in two formats:

#### Local Markdown Docs (always)

Create a `docs/` folder in the repo with these files:

| File | Content | Primary source |
|------|---------|---------------|
| `01-domain-glossary.md` | Business concepts, entity definitions, enum values, real data stats | Entities + Metabase |
| `02-entity-relationship.md` | Mermaid ER diagram, relationship descriptions | JPA/ORM entities |
| `03-api-endpoint-catalog.md` | All endpoints with method, path, description, request/response | Controllers |
| `04-transaction-lifecycle.md` | State machines, flow diagrams, sequence of operations | Services + Events |
| `05-event-flow.md` | Event types, queues, publish/subscribe mapping, sequence diagrams | Event handlers + message configs |
| `06-business-logic-details.md` | Formulas, calculations, special rules, edge cases | Domain services |

Adapt file names and content to what's relevant for the specific service. Not every service needs all files. A service without events doesn't need `05-event-flow.md`.

**Language**: Use the team's primary language. Technical terms in English are fine when they're clearer than the local translation.

#### Confluence Product Card (if user opted in)

Follow the Product Card template if one exists in the team's Confluence. Create audience-specific pages:

- **Overview**: Summary, key metrics from real data, dependencies
- **CS & Support**: Plain-language explanation, FAQ, error handling, escalation
- **Marketing & Growth**: Selling points, user segments, real product stats
- **Finance & Treasury**: Formulas with worked examples, settlement flow, reconciliation
- **Technical**: Architecture, DB schema, API summary, config flags, edge cases
- **Operations**: Batch jobs, runbooks, monitoring links, incident response

### Phase 4: Verification Checklist

**This is a required output.** Generate a checklist of all ❓ and ⚠️ items that need human verification:

```markdown
## Verification Checklist

### ❓ Unknown — Needs human input
- [ ] Which EOD endpoint does the scheduler call? (v1/v2/v3/v4 all exist)
- [ ] What time do batch jobs run? (no schedule config in repo)
- [ ] Who is the product owner?

### ⚠️ Inferred — Should verify
- [ ] Interest formula: `amount × rate / 365 × days` (from SavingBook.java:270)
- [ ] Weekend rule: Friday/Saturday skip deposits (from DateHandler.java:54)
- [ ] Prod Redis host: 172.31.17.119 (from application-prod.properties, may be overridden)
```

Present this checklist to the user at the end. These are the items where human knowledge is needed to upgrade ⚠️ → ✅ or resolve ❓.

## Handling Ambiguity

When you encounter something ambiguous, follow this decision tree:

```
Can I query real data (Metabase)?
├─ YES → Query it. If data confirms code → ✅
│         If data contradicts code → Report discrepancy, mark ❓
└─ NO
    Can I cross-reference 2+ code sources?
    ├─ YES → If they agree → ⚠️
    │         If they disagree → Report both, mark ❓
    └─ NO → Mark ⚠️ with source reference
              If multiple interpretations possible → Mark ❓, list all
```

**Never silently pick one interpretation.** If you're tempted to write "This does X" when it might also do Y, write "This does X ⚠️ (could also be Y — see [file:line])".

## Tone and Approach

- Write for someone who just joined the team and needs to understand the system quickly
- Lead with the business concept, then the technical detail
- Include real numbers from Metabase when available — "465K sổ đang mở (~592 tỷ VND)" is more useful than "many saving books"
- Flag anomalies from real data — stuck transactions, unexpected statuses, unused enum values — these are often the most valuable findings
- Don't clean up or editorialize what you find. If the code is messy or has 6 versions of the same endpoint, document that reality
