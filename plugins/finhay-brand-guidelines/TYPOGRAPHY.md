# Finhay Typography System - Complete Reference

This file contains complete typography specifications for the Finhay design system.

## Typeface

**Primary Font**: Inter
- **Source**: Google Fonts
- **URL**: https://fonts.google.com/specimen/Inter
- **Designer**: Rasmus Andersson
- **License**: Open Font License
- **Characteristics**: Excellent screen readability, comprehensive Unicode support, optimized for UI

### Vietnamese Support

Inter provides full support for Vietnamese diacritics:
- Base characters: a ă â b c d đ e ê g h i k l m n o ô ơ p q r s t u ư v x y
- All tone marks: á à ả ã ạ
- Combined diacritics: ằ ắ ẳ ẵ ặ ầ ấ ẩ ẫ ậ ề ế ể ễ ệ ồ ố ổ ỗ ộ ờ ớ ở ỡ ợ ừ ứ ử ữ ự

### Weights Used

- **Thin (100)**: Special decorative use only
- **ExtraLight (200)**: Light accents
- **Light (300)**: Subtle text
- **Regular (400)**: Body text, general content
- **Medium (500)**: Slightly emphasized text
- **SemiBold (600)**: Emphasis, highlights, headings
- **Bold (700)**: Display text, strong emphasis
- **ExtraBold (800)**: Very strong emphasis
- **Black (900)**: Maximum impact

**Most commonly used:** Regular (400), SemiBold (600), Bold (700)

## Secondary Font

**Secondary Font**: MTD Adventures
- **Type**: Decorative/Handwritten style
- **Usage**: Taglines, special headlines, creative callouts
- **Restrictions**: NOT for body text, UI, or long-form content

### When to Use MTD Adventures

✓ **Appropriate uses:**
- Taglines and slogans
- Creative campaign headlines
- Decorative accents in marketing materials
- Special event announcements
- Informal, friendly emphasis

✗ **Do not use for:**
- Body text or paragraphs
- UI elements (buttons, labels, navigation)
- Form fields or inputs
- Legal text or disclaimers
- Technical documentation

### Example Usage

```
Primary Font (Inter):
"Đầu tư thông minh, lợi nhuận bền vững"

Secondary Font (MTD Adventures):
"Bền vững" (as decorative tagline element)
"Gần gũi • Thân thiện • Dễ thương"
```

### Font Loading

**Web Implementation**:
```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet">
```

**CSS**:
```css
body {
  font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
}
```

## Typography Hierarchy

### Display Styles

Large, decorative headings for hero sections and landing pages.

#### Display 1
- **Size**: 120px
- **Line Height**: 160px (1.33)
- **Weight**: Bold (700)
- **Letter Spacing**: -0.02em (tight)
- **Usage**: Hero headlines, main landing page title
- **Max Width**: 800px recommended
- **Example**: "Đầu tư thông minh, Tương lai rực rỡ"

**CSS**:
```css
.display-1 {
  font-family: 'Inter', sans-serif;
  font-size: 120px;
  line-height: 160px;
  font-weight: 700;
  letter-spacing: -0.02em;
}
```

#### Display 2
- **Size**: 76px
- **Line Height**: 92px (1.21)
- **Weight**: SemiBold (600)
- **Letter Spacing**: -0.01em
- **Usage**: Section heroes, major feature highlights
- **Max Width**: 700px recommended
- **Example**: "Tiết kiệm và đầu tư dễ dàng"

**CSS**:
```css
.display-2 {
  font-family: 'Inter', sans-serif;
  font-size: 76px;
  line-height: 92px;
  font-weight: 600;
  letter-spacing: -0.01em;
}
```

#### Display 3
- **Size**: 60px
- **Line Height**: 76px (1.27)
- **Weight**: SemiBold (600)
- **Letter Spacing**: -0.01em
- **Usage**: Large section titles, promotional headers
- **Max Width**: 600px recommended
- **Example**: "Quản lý tài chính cá nhân"

**CSS**:
```css
.display-3 {
  font-family: 'Inter', sans-serif;
  font-size: 60px;
  line-height: 76px;
  font-weight: 600;
  letter-spacing: -0.01em;
}
```

### Heading Styles

Page and section titles maintaining clear information hierarchy.

#### Heading 1 (H1)
- **Size**: 36px
- **Line Height**: 44px (1.22)
- **Weight**: SemiBold (600)
- **Letter Spacing**: Normal
- **Usage**: Page titles, main section headers
- **Max Width**: 800px recommended
- **Frequency**: Once per page

**CSS**:
```css
h1, .heading-1 {
  font-family: 'Inter', sans-serif;
  font-size: 36px;
  line-height: 44px;
  font-weight: 600;
}
```

#### Heading 2 (H2)
- **Size**: 32px
- **Line Height**: 40px (1.25)
- **Weight**: SemiBold (600)
- **Letter Spacing**: Normal
- **Usage**: Major section headers
- **Max Width**: 700px recommended
- **Frequency**: Multiple per page

**CSS**:
```css
h2, .heading-2 {
  font-family: 'Inter', sans-serif;
  font-size: 32px;
  line-height: 40px;
  font-weight: 600;
}
```

#### Heading 3 (H3)
- **Size**: 28px
- **Line Height**: 36px (1.29)
- **Weight**: SemiBold (600)
- **Letter Spacing**: Normal
- **Usage**: Subsection headers
- **Max Width**: 600px recommended

**CSS**:
```css
h3, .heading-3 {
  font-family: 'Inter', sans-serif;
  font-size: 28px;
  line-height: 36px;
  font-weight: 600;
}
```

#### Heading 4 (H4)
- **Size**: 24px
- **Line Height**: 32px (1.33)
- **Weight**: SemiBold (600)
- **Letter Spacing**: Normal
- **Usage**: Card titles, small section headers
- **Max Width**: 500px recommended

**CSS**:
```css
h4, .heading-4 {
  font-family: 'Inter', sans-serif;
  font-size: 24px;
  line-height: 32px;
  font-weight: 600;
}
```

### Body Styles

Main content text - the most frequently used typography.

#### Body 1
- **Size**: 20px
- **Line Height**: 30px (1.5)
- **Weight**: Regular (400) / SemiBold (600) for highlights
- **Letter Spacing**: Normal
- **Usage**: Primary paragraphs, main content, introductions
- **Max Width**: 680px recommended (65-75 characters per line)

**Variants**:
```css
.body-1 {
  font-family: 'Inter', sans-serif;
  font-size: 20px;
  line-height: 30px;
  font-weight: 400;
}

.body-1-highlight {
  font-family: 'Inter', sans-serif;
  font-size: 20px;
  line-height: 30px;
  font-weight: 600;
}
```

#### Body 2
- **Size**: 18px
- **Line Height**: 28px (1.56)
- **Weight**: Regular (400) / SemiBold (600) for highlights
- **Letter Spacing**: Normal
- **Usage**: Secondary paragraphs, card content, descriptions
- **Max Width**: 640px recommended

**Variants**:
```css
.body-2 {
  font-family: 'Inter', sans-serif;
  font-size: 18px;
  line-height: 28px;
  font-weight: 400;
}

.body-2-highlight {
  font-family: 'Inter', sans-serif;
  font-size: 18px;
  line-height: 28px;
  font-weight: 600;
}
```

#### Body 3
- **Size**: 16px
- **Line Height**: 24px (1.5)
- **Weight**: Regular (400) / SemiBold (600) for highlights
- **Letter Spacing**: Normal
- **Usage**: UI text, form labels, button text, compact content
- **Max Width**: 600px recommended

**Variants**:
```css
.body-3 {
  font-family: 'Inter', sans-serif;
  font-size: 16px;
  line-height: 24px;
  font-weight: 400;
}

.body-3-highlight {
  font-family: 'Inter', sans-serif;
  font-size: 16px;
  line-height: 24px;
  font-weight: 600;
}
```

### Caption Styles

Supplementary information, metadata, and annotations.

#### Caption
- **Size**: 14px
- **Line Height**: 20px (1.43)
- **Weight**: Regular (400) / SemiBold (600) for highlights
- **Letter Spacing**: Normal
- **Usage**: Metadata, help text, image captions, timestamps
- **Color**: Use secondary text color (#999999 on dark, #666666 on light)

**Variants**:
```css
.caption {
  font-family: 'Inter', sans-serif;
  font-size: 14px;
  line-height: 20px;
  font-weight: 400;
  color: var(--text-secondary);
}

.caption-highlight {
  font-family: 'Inter', sans-serif;
  font-size: 14px;
  line-height: 20px;
  font-weight: 600;
}
```

#### Tiny Caption
- **Size**: 12px
- **Line Height**: 16px (1.33)
- **Weight**: Regular (400) / SemiBold (600) for highlights
- **Letter Spacing**: 0.01em
- **Usage**: Small labels, badges, legal text, footnotes
- **Minimum Size**: Do not go smaller than 12px for accessibility

**Variants**:
```css
.tiny-caption {
  font-family: 'Inter', sans-serif;
  font-size: 12px;
  line-height: 16px;
  font-weight: 400;
  letter-spacing: 0.01em;
  color: var(--text-secondary);
}

.tiny-caption-highlight {
  font-family: 'Inter', sans-serif;
  font-size: 12px;
  line-height: 16px;
  font-weight: 600;
  letter-spacing: 0.01em;
}
```

## Typography Guidelines

### Hierarchy Usage

**Display**
- Use: Hero sections, landing pages, major announcements
- Frequency: Rare, high-impact moments
- Pairing: With Body 1 or Body 2 for supporting text

**Heading**
- Use: Structure content hierarchy (H1 > H2 > H3 > H4)
- Frequency: Multiple per page to organize content
- Pairing: With Body text for content, Caption for metadata

**Body**
- Use: Main content, paragraphs, descriptions
- Frequency: Most common text style (80% of content)
- Pairing: With Caption for supplementary info

**Caption**
- Use: Metadata, labels, annotations, help text
- Frequency: Supporting information
- Pairing: With Body or Heading text

### Best Practices

#### Consistency
- Maintain same text styles across similar contexts
- Use the same heading levels for similar content types
- Keep emphasis patterns consistent (SemiBold for highlight)

#### Readability
- Line Height: Minimum 1.5 for body text
- Line Length: 65-75 characters for optimal readability
- Paragraph Spacing: 1.5-2x line height between paragraphs
- Never use ALL CAPS for body text

#### Emphasis
- Primary Emphasis: Use SemiBold (600) weight
- Secondary Emphasis: Use color (brand green #49D82F)
- Avoid: Underlining (except for links), italics for Vietnamese text

#### Accessibility
- Minimum Size: 14px for body, 12px for captions
- Contrast: 4.5:1 minimum with background (WCAG AA)
- Don't rely on color alone for meaning
- Test with screen readers for Vietnamese content

### Spacing Guidelines

#### Vertical Rhythm

**Display to Body**: 32-48px
**Heading to Body**: 16-24px
**Body to Body**: 16px (1x line height)
**Paragraph Spacing**: 24-30px
**Section Spacing**: 48-80px

**CSS Example**:
```css
h1 { margin-bottom: 24px; }
h2 { margin-bottom: 20px; }
h3 { margin-bottom: 16px; }
p { margin-bottom: 16px; }
.section { margin-bottom: 64px; }
```

#### Horizontal Spacing

- **Letter Spacing**: Generally normal, tight for large display text
- **Word Spacing**: Use default, don't adjust
- **Line Length**: 65-75 characters for body text

### Responsive Typography

#### Desktop (1440px+)
- Display: Full sizes
- Headings: Full sizes
- Body: Body 1 or Body 2 preferred
- Caption: Standard sizes

#### Tablet (768px - 1439px)
- Display: Reduce by 25-30%
- Headings: Reduce H1 to 32px, others proportionally
- Body: Body 2 or Body 3 preferred
- Caption: Standard sizes

#### Mobile (< 768px)
- Display: Display 3 becomes H1, others scale down
- Headings: H1: 28px, H2: 24px, H3: 20px
- Body: Body 3 (16px) preferred for space efficiency
- Caption: Standard sizes minimum

**Responsive CSS Example**:
```css
h1 {
  font-size: 36px;
  line-height: 44px;
}

@media (max-width: 768px) {
  h1 {
    font-size: 28px;
    line-height: 36px;
  }
}
```

## Platform-Specific Guidelines

### Web (HTML/CSS)

- Use Google Fonts CDN for Inter
- Implement font-display: swap for performance
- Use rem units for scalability
- Define CSS variables for reusability

### Documents (DOCX, PDF)

- Embed Inter font if possible
- Fallback to system sans-serif if Inter unavailable
- Use Word/PDF styles for consistency
- Maintain same size/weight specifications

### Presentations (PPTX)

- Embed Inter font in presentation
- Larger sizes: Display and H1 for slides
- Body 2/3 for content slides
- Caption for footnotes and sources

### Design Tools (Figma)

- Install Inter font locally
- Create text styles matching this system
- Use Auto Layout with proper spacing
- Share styles across team libraries

## Vietnamese-Specific Considerations

### Diacritics
- Inter renders all Vietnamese diacritics correctly
- Test all tone combinations: á à ả ã ạ
- Test combined diacritics: ằ ắ ẳ ẵ ặ
- Ensure proper vertical spacing with diacritics

### Sentence Structure
- Vietnamese sentences may be longer than English
- Allow more line height for readability
- Test wrapping behavior with long Vietnamese words

### Cultural Preferences
- Vietnamese readers prefer clear, direct language
- Use proper formal/informal forms based on context
- Number formatting: 1.000.000 (period as thousands separator)

## Technical Implementation

### CSS Variables
```css
:root {
  /* Font Family */
  --font-primary: 'Inter', -apple-system, sans-serif;
  
  /* Display */
  --display-1: 700 120px/160px var(--font-primary);
  --display-2: 600 76px/92px var(--font-primary);
  --display-3: 600 60px/76px var(--font-primary);
  
  /* Headings */
  --heading-1: 600 36px/44px var(--font-primary);
  --heading-2: 600 32px/40px var(--font-primary);
  --heading-3: 600 28px/36px var(--font-primary);
  --heading-4: 600 24px/32px var(--font-primary);
  
  /* Body */
  --body-1: 400 20px/30px var(--font-primary);
  --body-2: 400 18px/28px var(--font-primary);
  --body-3: 400 16px/24px var(--font-primary);
  
  /* Caption */
  --caption: 400 14px/20px var(--font-primary);
  --tiny-caption: 400 12px/16px var(--font-primary);
}
```

### Design Tokens
```json
{
  "typography": {
    "fontFamily": {
      "primary": "Inter, -apple-system, sans-serif"
    },
    "display": {
      "1": {
        "fontSize": "120px",
        "lineHeight": "160px",
        "fontWeight": "700"
      }
    },
    "heading": {
      "1": {
        "fontSize": "36px",
        "lineHeight": "44px",
        "fontWeight": "600"
      }
    }
  }
}
```
