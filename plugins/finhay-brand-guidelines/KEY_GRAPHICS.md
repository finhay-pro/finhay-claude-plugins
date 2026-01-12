# Finhay Key Graphics & Illustration Style

Guidelines for visual graphics, patterns, and illustration style that reinforce the Finhay brand identity.

## Finlight - Brand Graphic System

The **Finlight** system is Finhay's signature graphic element, derived from the logo's leaf symbol. It creates visual consistency and brand recognition across all touchpoints.

### Origin & Meaning

The Finlight pattern comes from the logo's two-leaf symbol, representing:
- **Light** - Illumination, clarity, guidance in financial decisions
- **Growth** - The leaf symbol's connection to natural growth
- **Energy** - Dynamic, forward-moving visual language
- **Trust** - Consistent visual element builds recognition

### Finlight Variants

| Type | Name (Vietnamese) | Description | Best For |
|------|-------------------|-------------|----------|
| **A** | Mảng Finlight | Solid leaf shapes with gradient fills | Large backgrounds, hero sections, app screens |
| **B** | Đường Finlight | Line-based leaf outlines | Subtle accents, borders, dividers |
| **C** | Đường Finlight Hội Tụ | Converging lines toward center | Focus points, CTAs, attention grabbing |
| **D** | Finlight Lan Toả | Radiating patterns outward | Celebration, expansion themes, achievements |

### Visual Reference

```
Type A - Mảng Finlight (Solid)
┌─────────────────────┐
│     ╭──────╮        │
│   ╭─┤ SOLID├─╮      │
│   │ ╰──────╯ │      │
│   ╰──────────╯      │
└─────────────────────┘

Type B - Đường Finlight (Lines)
┌─────────────────────┐
│     ╭──────╮        │
│   ╭─┤ LINE ├─╮      │
│   │ ╰──────╯ │      │
│   ╰──────────╯      │
└─────────────────────┘

Type C - Hội Tụ (Converging)
┌─────────────────────┐
│   ╲  │  ╱           │
│    ╲ │ ╱            │
│     ╲│╱             │
│      ●              │
└─────────────────────┘

Type D - Lan Toả (Radiating)
┌─────────────────────┐
│      ╱│╲            │
│     ╱ │ ╲           │
│    ●──●──●          │
│     ╲ │ ╱           │
└─────────────────────┘
```

### Application Guidelines

#### On Brand Green Backgrounds (#298C1B, #1E5613)

| Variant | Color Treatment |
|---------|-----------------|
| Mảng Finlight | Lighter green tints (#8BE379, #4CD137) or white |
| Đường Finlight | Bright green (#4CD137) or white strokes |
| Hội Tụ | White or light green lines |
| Lan Toả | Gradient from white to transparent |

#### On Light Backgrounds (White, #D9F5D3)

| Variant | Color Treatment |
|---------|-----------------|
| Mảng Finlight | Brand greens (#4CD137, #3DAD26) with gradients |
| Đường Finlight | Brand green (#4CD137) strokes |
| Hội Tụ | Dark green (#1E5613) or brand green lines |
| Lan Toả | Green gradient outward |

### Finlight Usage Rules

**Do:**
- Use as supporting visual element
- Maintain 45° angle consistency with logo
- Apply appropriate opacity (20-80%) for subtlety
- Use brand-approved colors only
- Scale proportionally

**Don't:**
- Use as the primary focal point (logo takes priority)
- Change the angle of leaf shapes
- Use non-brand colors
- Overcrowd with multiple Finlight elements
- Make it compete with the logo
- Distort or stretch the shapes

### Opacity Guidelines

| Context | Recommended Opacity |
|---------|---------------------|
| Background texture | 10-20% |
| Subtle accent | 20-40% |
| Decorative element | 40-60% |
| Featured graphic | 60-80% |
| Primary element | 80-100% |

## Illustration Style: Semi-Flat Design

Finhay uses **Semi-Flat Design**, which combines the simplicity of flat design with subtle depth elements for a modern, friendly look.

### What is Semi-Flat Design?

Semi-Flat Design inherits the minimalist spirit of Flat Design but adds:
- Subtle shadows for depth
- Gradient fills for dimension
- Layering for visual hierarchy
- Noise texture for organic feel
- Glass effects for modern touch

### Core Design Principles

#### 1. Geometric Shapes

Use basic geometric forms as building blocks:
- Circles and semicircles
- Rectangles and squares
- Triangles
- Rounded organic shapes (leaf-inspired)

```
Basic Shapes:
○  □  △  ◇  ▭
```

#### 2. Rounded Corners

All shapes should have soft, rounded corners:

| Element Size | Corner Radius |
|--------------|---------------|
| Small (icons, buttons) | 8-16px |
| Medium (cards, containers) | 16-24px |
| Large (sections, backgrounds) | 24-32px |

#### 3. Layering

Create depth through overlapping elements:
- Background layer (largest, most subtle)
- Middle layer (supporting elements)
- Foreground layer (primary focus)

Each layer should have slightly different color values or opacity.

#### 4. Gradients

Apply gradients for dimension:
- **Direction**: 45° or 135° (matching logo angle)
- **Colors**: 2-3 tones from the same color family
- **Transition**: Smooth, not harsh

```css
/* Example gradient */
background: linear-gradient(135deg, #4CD137 0%, #3DAD26 50%, #1E5613 100%);
```

#### 5. Noise Texture

Add subtle noise overlay for organic feel:
- **Amount**: 2-5% noise
- **Blend mode**: Overlay or Soft Light
- **Purpose**: Reduces digital "flatness"

#### 6. Glass Effects

Apply glass/frosted effects for modern UI:
- Light reflection on edges
- Subtle blur for depth
- Transparency for layered look

```css
/* Glass effect example */
background: rgba(255, 255, 255, 0.1);
backdrop-filter: blur(10px);
border: 1px solid rgba(255, 255, 255, 0.2);
```

### Illustration Elements

#### Icon Style

| Attribute | Specification |
|-----------|---------------|
| Base | Geometric shapes |
| Stroke weight | 2px (standard), 3px (emphasis) |
| Corners | Rounded (8px radius) |
| Fill | Two-tone or gradient |
| Accents | Optional sparkle/star elements |

#### Character/Mascot Style

If creating character illustrations:
- Simplified, geometric forms
- Friendly expressions
- Brand colors dominant
- No excessive detail
- Consistent proportions across all characters

### Color in Illustrations

#### Primary Elements
- Use brand green gradients (#4CD137 → #1E5613)
- White or light accents for highlights

#### Secondary Elements
- Neutral colors for supporting shapes
- Complementary accent colors sparingly

#### Accents & Highlights
- Orange (#FA8C27) for attention
- Yellow for warmth and energy
- White for light/reflection effects

#### Line Work
- Brand green (#4CD137) or white for strokes
- Consistent stroke width throughout

## App Illustrations

### Dark Mode

| Element | Specification |
|---------|---------------|
| Background | Neutral 900 (#0D0E10) |
| Primary shapes | Green gradients with glass effects |
| Text | White (#FFFFFF) |
| Accents | Bright green highlights (#4CD137) |
| Shadows | Darker values, subtle glow effects |

### Light Mode

| Element | Specification |
|---------|---------------|
| Background | White (#FFFFFF) or Neutral 100 |
| Primary shapes | Green gradients (same as dark) |
| Text | Neutral 900 (#0D0E10) |
| Accents | Brand green highlights |
| Shadows | Light gray, soft drop shadows |

### System State Illustrations

| State | Icon Style | Colors | Mood |
|-------|------------|--------|------|
| **Success** | Checkmark, upward elements, stars | Green gradient | Celebratory |
| **Error** | X mark, warning triangle | Orange/Red gradient | Cautious but not scary |
| **Loading** | Circular, hourglass, progress | Green gradient | Patient, active |
| **Empty** | Question mark, documents, search | Blue gradient | Helpful, guiding |
| **Maintenance** | Tools, gears, construction | Orange gradient | Temporary, working |

### Example Compositions

#### Success State
```
Elements:
- Central checkmark (green gradient)
- Radiating lines (Finlight Lan Toả)
- Sparkle accents
- Upward-pointing shapes

Colors:
- Primary: #4CD137 → #3DAD26
- Accents: White sparkles
- Background glow: Light green
```

#### Error State
```
Elements:
- X mark or warning triangle
- Subdued Finlight elements
- No celebratory sparkles

Colors:
- Primary: #FA8C27 → #E98E00
- Text: Dark for readability
- Background: Neutral
```

## Photography Style

### Human Subjects

#### Expression & Mood
- **Expression**: Smiling, friendly, approachable
- **Mood**: Optimistic, confident, relaxed
- **Energy**: Positive but not over-the-top

#### Demographics
- **Age**: Young adults (25-40, Finhay's target demographic)
- **Diversity**: Representative of Vietnamese users
- **Relatability**: Everyday people, not obviously models

#### Styling
- **Clothing**: Smart casual, modern
- **Colors**: Preferably incorporating brand green
- **Accessories**: Minimal, not distracting
- **Setting**: Clean, contemporary environments

### Photography Do's

✓ Natural, soft lighting
✓ Clean, simple backgrounds
✓ Authentic expressions and poses
✓ Brand color accents in scene (green elements)
✓ Technology in use (phones showing app)
✓ Real-life financial moments (saving, planning)
✓ Group shots showing connection

### Photography Don'ts

✗ Overly formal/corporate style (suits, boardrooms)
✗ Complex, busy backgrounds
✗ Staged or obviously fake expressions
✗ Stock photo clichés (pointing at charts)
✗ Non-brand color dominance
✗ Dark, moody lighting
✗ Excessive editing/filters

### Photo Treatment

When using photography with brand elements:

1. **Color grading**: Slightly enhance greens
2. **Overlay**: Can add subtle brand color overlay (10-20%)
3. **Integration**: Finlight elements can overlay photos
4. **Logo placement**: Ensure contrast with photo background

## Design Assets

### Background Assets

Located in `assets/backgrounds/`:

| File | Path | Description | Usage |
|------|------|-------------|-------|
| Gradient 01 | `assets/backgrounds/gradient-01.jpg` | Light-to-green, diagonal flow | Hero sections, headers, onboarding |
| Gradient 02 | `assets/backgrounds/gradient-02.jpg` | Green-to-dark, vertical | Premium content, footers, dark themes |
| Gradient 03 | `assets/backgrounds/gradient-03.jpg` | Light fade, soft subtle | Cards, modals, subtle backgrounds |

### Logo Assets

Located in `assets/logos/`:

| File | Path | Best For |
|------|------|----------|
| Horizontal Green | `assets/logos/finhay-horizontal-green.png` | Logo and name place horizontal, green backgrounds |
| Horizontal Dark Green | `assets/logos/finhay-horizontal-dark-green.png` | Logo and name place horizontal, dark green background |
| Horizontal White | `assets/logos/finhay-horizontal-white.png` | Logo and name place horizontal, white background |
| Horizontal Black Text Transparent | `assets/logos/finhay-horizontal-black-text-transparent.png` | Logo and name place horizontal, transparent background, black text |
| Horizontal White Text Transparent | `assets/logos/finhay-horizontal-white-text-transparent.png` | Logo and name place horizontal, transparent background, white text |
| Vertical Green | `assets/logos/finhay-vertical-green.png` | Logo and name place vertical, green background |
| Vertical Dark Green | `assets/logos/finhay-vertical-dark-green.png` | Logo and name place vertical, dark green background |
| Vertical White | `assets/logos/finhay-vertical-white.png` | Logo and name place vertical, white background |
| Vertical Black Text Transparent | `assets/logos/finhay-vertical-black-text-transparent.png` | Logo and name place vertical, transparent background, black text |
| Vertical White Text Transparent | `assets/logos/finhay-vertical-white-text-transparent.png` | Logo and name place vertical, transparent background, white text |
| Symbol Green | `assets/logos/finhay-symbol-green.png` | Logo without name, green background |
| Symbol Dark Green | `assets/logos/finhay-symbol-dark-green.png` | Logo without name, dark green background |
| Symbol White | `assets/logos/finhay-symbol-white.png` | Logo without name, white background |
| Symbol Transparent | `assets/logos/finhay-symbol-transparent.png` | Logo without name, transparent background |

### Asset + Background Combinations

| Background | Logo | Result |
|------------|------|--------|
| `gradient-01.jpg` | `finhay-horizontal-green.png` | Standard marketing hero |
| `gradient-02.jpg` | `finhay-horizontal-white.png` | Premium dark theme |
| `gradient-03.jpg` | `finhay-horizontal-green.png` | Subtle, light presentation |

See [LOGO_GUIDELINES.md](LOGO_GUIDELINES.md) for complete logo specifications.

## Design Checklist

When creating branded graphics:

### Style
- [ ] Uses Semi-Flat Design principles
- [ ] Geometric shapes with rounded corners
- [ ] Gradients at correct angles (45°/135°)
- [ ] Appropriate layering and depth
- [ ] Noise texture applied subtly (if applicable)

### Colors
- [ ] Colors from approved palettes
- [ ] Gradients within same color family
- [ ] Sufficient contrast for readability
- [ ] Dark/light mode versions if needed

### Brand Elements
- [ ] Finlight elements used appropriately
- [ ] Logo follows usage guidelines
- [ ] Brand personality reflected

### Technical
- [ ] Works at all required sizes
- [ ] Vietnamese text renders correctly
- [ ] Exports in required formats
- [ ] Consistent with other Finhay materials

### Accessibility
- [ ] Color contrast meets WCAG AA (4.5:1 minimum)
- [ ] Not relying solely on color for meaning
- [ ] Clear visual hierarchy
