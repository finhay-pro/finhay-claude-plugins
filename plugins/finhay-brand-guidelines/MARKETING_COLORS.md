# Finhay Marketing Colors

Colors for print, marketing materials, social media, and brand communications.

> **Note**: These colors differ from App/Web UI colors. Use this palette for print materials, marketing campaigns, social media graphics, and brand communications. For digital product interfaces, see [COLOR_SCALES.md](COLOR_SCALES.md).

## Primary Brand Colors (Logo-derived)

These colors are extracted from the official Finhay logo and represent the core brand identity.

| Name | Hex | RGB | CMYK | Usage |
|------|-----|-----|------|-------|
| Bright Green | `#4CD137` | 76, 209, 55 | 53/0/100/0 | Primary logo color, main CTAs, headlines |
| Medium Green | `#3DAD26` | 61, 173, 38 | 70/0/100/25 | Supporting elements, hover states |
| Dark Green | `#1E5613` | 30, 86, 19 | 80/30/100/40 | Deep backgrounds, premium/formal contexts |

### Logo Color Breakdown

| Logo Element | Hex | Description |
|--------------|-----|-------------|
| Leaf 1 (bright) | `#4CD137` | Front/top leaf |
| Leaf 2 (light) | `#8BE379` | Back/bottom leaf |
| Overlap area | `#3DAD26` | Where leaves intersect |
| Wordmark (light bg) | `#000000` | Black text on light |
| Wordmark (dark bg) | `#FFFFFF` | White text on dark |

## Marketing Background Colors

| Name | Hex | RGB | Usage |
|------|-----|-----|-------|
| Brand Green | `#298C1B` | 41, 140, 27 | Primary marketing backgrounds, banners |
| Dark Green | `#1E5613` | 30, 86, 19 | Premium/formal backgrounds, headers |
| Light Green 100 | `#D9F5D3` | 217, 245, 211 | Soft backgrounds, cards, sections |
| Light Green 200 | `#B6EFAC` | 182, 239, 172 | Subtle highlights, hover states |

## Secondary Accent Colors

Use these colors sparingly for emphasis, CTAs, and specific semantic purposes.

| Color | Hex | RGB | CMYK | Usage |
|-------|-----|-----|------|-------|
| Orange | `#FA8C27` | 250, 140, 39 | 2/53/100/0 | Promotions, urgency, secondary CTAs |
| Red | `#B22222` | 178, 34, 34 | 22/99/100/15 | Errors, important alerts, warnings |
| Blue | `#285CDE` | 40, 92, 222 | 80/67/0/0 | Trust indicators, info, links |
| Purple | `#5D3FD3` | 93, 63, 211 | 75/78/0/0 | Premium features, special content |

### Semantic Usage

| Purpose | Primary Color | Background Color |
|---------|---------------|------------------|
| Success/Positive | Green `#3AC45C` | Light Green `#D8F3DE` |
| Error/Negative | Red `#B22222` | Light Red `#FBD9D7` |
| Warning/Caution | Orange `#FA8C27` | Light Orange `#FBE8CC` |
| Information | Blue `#285CDE` | Light Blue `#D4EAFF` |
| Premium/Special | Purple `#5D3FD3` | Light Purple `#F0DDF9` |

## Gradient System

Gradients add depth and visual interest to marketing materials.

### Harmonious Gradients (Same Color Family)

Use for smooth, professional backgrounds:

```css
/* Light to Dark Green */
background: linear-gradient(135deg, #4CD137 0%, #1E5613 100%);

/* Light Green Fade */
background: linear-gradient(180deg, #D9F5D3 0%, #4CD137 100%);

/* Orange to Yellow */
background: linear-gradient(135deg, #FA8C27 0%, #E9CB36 100%);
```

### Contrasting Gradients (Different Colors)

Use for dynamic, energetic designs:

```css
/* Green to Blue */
background: linear-gradient(135deg, #4CD137 0%, #285CDE 100%);

/* Green to Purple */
background: linear-gradient(135deg, #4CD137 0%, #5D3FD3 100%);
```

### Background Gradient Assets

Pre-made gradient backgrounds located in `assets/backgrounds/`:

| File | Path | Description | Usage |
|------|------|-------------|-------|
| Gradient 01 | `assets/backgrounds/gradient-01.jpg` | Light-to-green, diagonal | Hero sections, headers |
| Gradient 02 | `assets/backgrounds/gradient-02.jpg` | Green-to-dark, vertical | Premium content, footers |
| Gradient 03 | `assets/backgrounds/gradient-03.jpg` | Light fade, soft | Subtle backgrounds, cards |

### Logo Pairing with Gradients

| Background | Recommended Logo |
|------------|------------------|
| `gradient-01.jpg` | `assets/logos/finhay-horizontal-green.png` |
| `gradient-02.jpg` | `assets/logos/finhay-horizontal-white.png` |
| `gradient-03.jpg` | `assets/logos/finhay-horizontal-green.png` |

## Color Ratio Guidelines

### Standard Design Layout (60-30-10 Rule)

| Percentage | Role | Colors |
|------------|------|--------|
| **60%** | Primary/Dominant | Background or main color (e.g., Brand Green, White) |
| **30%** | Secondary/Supporting | Complementary elements (e.g., Dark Green, Light Green) |
| **10%** | Accent/Highlight | CTAs, emphasis (e.g., Orange 5-7%, others 3-5%) |

### Example Applications

**Marketing Banner:**
- 60%: White background
- 30%: Brand Green sections
- 10%: Orange CTA button

**Social Media Post:**
- 60%: Brand Green background
- 30%: White/Light Green content areas
- 10%: Dark Green accents, Orange highlights

### Partner/Co-branded Content

| Platform | Finhay Colors | Partner Colors |
|----------|---------------|----------------|
| Finhay's channels | 70% | 30% |
| Joint campaigns | 50% | 50% |
| Partner's channels | Min 20% | Up to 80% |

**Rules:**
- Finhay logo must always be visible
- Brand green should appear even at minimum ratio
- Never let partner colors dominate on Finhay channels

### Event/Holiday Content

| Event Type | Brand Colors | Event/Holiday Colors |
|------------|--------------|----------------------|
| Regular events/promotions | 80% | 20% |
| Cultural events (Tết, Mid-Autumn) | 60% | 40% |
| National holidays | 60% | 40% |

**Cultural Color Notes:**
- Tết: Red and gold are traditional, balance with brand green
- Mid-Autumn: Yellow/orange moon themes acceptable
- National holidays: Red/yellow flag colors, use respectfully

## Print Specifications

### CMYK Values for Professional Print

| Color | CMYK | Pantone (Approximate) |
|-------|------|----------------------|
| Bright Green | C53 M0 Y100 K0 | Pantone 361 C |
| Medium Green | C70 M0 Y100 K25 | Pantone 364 C |
| Dark Green | C80 M30 Y100 K40 | Pantone 357 C |
| Orange | C2 M53 Y100 K0 | Pantone 144 C |
| Red | C22 M99 Y100 K15 | Pantone 1805 C |
| Blue | C80 M67 Y0 K0 | Pantone 2728 C |
| Purple | C75 M78 Y0 K0 | Pantone 2685 C |

### Print Considerations

1. **Color Proofing**: Always request print proofs for brand-critical materials
2. **Paper Stock**: Colors appear differently on coated vs. uncoated paper
3. **Large Format**: Test colors at scale for billboards and banners
4. **Spot Colors**: Consider Pantone spot colors for exact brand matching

## Digital Specifications

### Hex Values for Digital Use

```css
:root {
  /* Primary Brand */
  --finhay-bright-green: #4CD137;
  --finhay-medium-green: #3DAD26;
  --finhay-dark-green: #1E5613;
  --finhay-brand-bg: #298C1B;
  
  /* Light Tints */
  --finhay-light-100: #D9F5D3;
  --finhay-light-200: #B6EFAC;
  
  /* Accents */
  --finhay-orange: #FA8C27;
  --finhay-red: #B22222;
  --finhay-blue: #285CDE;
  --finhay-purple: #5D3FD3;
}
```

### RGB Values for Video/Motion

| Color | RGB | Usage |
|-------|-----|-------|
| Bright Green | 76, 209, 55 | Primary on-screen brand |
| Dark Green | 30, 86, 19 | Lower thirds, backgrounds |
| Orange | 250, 140, 39 | Callouts, highlights |

## Accessibility Considerations

### Contrast Ratios (WCAG AA Compliance)

| Combination | Ratio | Status |
|-------------|-------|--------|
| White on Brand Green (#298C1B) | 4.7:1 | ✓ Pass |
| White on Dark Green (#1E5613) | 8.2:1 | ✓ Pass |
| Black on Light Green (#D9F5D3) | 15.1:1 | ✓ Pass |
| Bright Green on White | 2.8:1 | ✗ Fail for text |
| Bright Green on Dark Green | 4.1:1 | ~ Large text only |

### Recommendations

- Use white text on brand/dark green backgrounds
- Use black text on light green backgrounds
- Avoid bright green for body text (use for icons, accents)
- Always test contrast ratios for new combinations

## Color Application Examples

### Social Media Post

```
Background: Brand Green (#298C1B)
Headline: White (#FFFFFF)
Body text: White (#FFFFFF)
CTA Button: Orange (#FA8C27) with white text
Logo: White version
```

### Print Brochure

```
Cover: Dark Green (#1E5613) background
Headlines: Bright Green (#4CD137)
Body text: Black (#000000) on white pages
Accent elements: Orange (#FA8C27)
Charts/graphs: Multi-color palette
```

### Email Marketing

```
Header: Brand Green (#298C1B) with white logo
Body background: White (#FFFFFF)
Headline: Dark Green (#1E5613)
Body text: Black (#000000)
CTA Button: Bright Green (#4CD137) with white text
Footer: Light Green (#D9F5D3)
```
