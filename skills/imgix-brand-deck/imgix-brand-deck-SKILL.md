---
name: imgix-brand-deck
description: "Create on-brand Imgix slide decks (.pptx) that follow official brand guidelines. Use this skill whenever someone at Imgix needs to create a presentation, pitch deck, sales deck, account review, or any slides. This skill enforces Imgix's exact colors, typography, image treatment (padding, border radius), The Beam gradient bar, logo placement, and layout rules so every deck looks professional and consistent — no design guesswork needed. Trigger whenever the user mentions 'deck', 'slides', 'presentation', 'pitch', 'account review', or wants to create any Imgix-branded .pptx file."
---

# Imgix Brand Deck Skill

This skill creates on-brand Imgix presentations. Every slide must look like it came from the same design team. The brand identity is modern, dark, minimal, and precise — reflecting Imgix's position as a technical image platform.

Before creating any deck, also read the `pptx` skill's SKILL.md and its recommended creation guide (pptxgenjs.md) for the mechanics of building .pptx files. This skill provides the *brand rules* that sit on top of those technical instructions.

---

## Color Palette

### Primary Palette (use these for almost everything)

| Name       | Hex       | RGB             | Usage                                    |
|------------|-----------|-----------------|------------------------------------------|
| Off-Black  | `#1E1E23` | 30 / 30 / 35    | **Default slide background**             |
| Black      | `#000000` | 0 / 0 / 0       | Graphic accents only, not backgrounds    |
| Dark Gray  | `#807D7A` | 128 / 125 / 122 | Secondary text, muted labels             |
| Mid Gray   | `#BCB9B6` | 188 / 185 / 182 | Tertiary text, dividers                  |
| Light Gray | `#F8F5F2` | 248 / 245 / 242 | Light background variant, long-form text |
| White      | `#FFFFFF` | 255 / 255 / 255 | Primary text on dark backgrounds         |

### Secondary Palette (use sparingly — accents, gradients, data viz)

| Name   | Hex       | RGB             |
|--------|-----------|-----------------|
| Red    | `#FF3C00` | 255 / 60 / 0   |
| Yellow | `#FFB824` | 255 / 184 / 36 |
| Cream  | `#FFEABB` | 255 / 234 / 187 |
| Green  | `#59BB91` | 89 / 187 / 145 |
| Blue   | `#207593` | 32 / 117 / 147 |
| Navy   | `#131C34` | 19 / 28 / 52   |

### Color Weighting

Colors should be weighted heavily toward the gray palette. Off-Black dominates. Use secondary colors only as pops for emphasis — a chart accent, a highlighted stat, a gradient beam. Never use secondary colors as solid slide backgrounds or large fills.

### Color Don'ts
- No solid colors outside the brand palettes
- No adjusting transparency of brand colors
- No illegible color combinations (e.g., red text on green)
- No unapproved gradients
- No low-contrast type on images
- No logo on colors outside the palette

---

## Typography

### Font Selection

**Primary typeface: Circular** (by Lineto — requires license from lineto.com/typefaces/circular)
Weights: Book, Medium, Bold

**Alternative typeface: Plus Jakarta Sans** (free from Google Fonts)
Use when Circular is unavailable (e.g., in pptxgenjs which can't embed custom fonts).
Weight mapping: Plus Jakarta Sans Medium → Circular Book, Semi Bold → Medium, Bold → Bold.

When building decks programmatically, default to **Circular XX** (the installed licensed typeface). If Circular is not installed on the target machine, fall back to **Plus Jakarta Sans**.

### Type Hierarchy

| Level    | Font            | Weight    | Line Height | Tracking | Notes                    | Slide Size (approx) |
|----------|-----------------|-----------|-------------|----------|--------------------------|----------------------|
| Hero     | Circular/PJS    | Book      | 100%        | -3%      | Big impact statements     | 44-60pt             |
| Headline | Circular/PJS    | Medium    | 110%        | normal   | Slide titles              | 28-36pt             |
| Subhead  | Circular/PJS    | Book      | 100%        | ~2%      | ALL CAPS, section labels (charSpacing: 2 in pptxgenjs) | 12-14pt |
| Body     | Circular/PJS    | Book      | 140%        | normal   | Paragraphs, bullets       | 12-14pt             |
| Caption  | Circular/PJS    | Book      | 130%        | normal   | Footnotes, source labels  | 10-12pt             |

### Typography Rules
- Use a high-contrast approach: very large hero text paired with smaller accompanying text
- Left-align body text and bullets; center only hero/title text when it's a standalone statement
- Subheads are ALL CAPS with subtle letter spacing (charSpacing: 2, NOT wide) — they act as section labels (like "IMGIX.COM", "OUR MISSION"). **Do NOT place subheads above headlines on content slides** — subheads are reserved for the cover slide and section dividers only.
- Body text on dark backgrounds: White (#FFFFFF) or Light Gray (#F8F5F2)
- Body text on light backgrounds: Off-Black (#1E1E23) or Black (#000000)
- Ensure WCAG AA contrast compliance on all text

---

## Slide Layouts

### Default Slide Structure

Every slide should follow this general structure:

```
┌─────────────────────────────────────────────┐
│  [Imgix logo - bottom left]                 │
│                                             │
│     [Content area - generous margins]       │
│                                             │
│                                             │
│                                     [page#] │
│ ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓ THE BEAM ▓▓▓▓▓▓▓▓▓▓▓▓▓▓ │
└─────────────────────────────────────────────┘
```

- **Background**: Off-Black (#1E1E23) is the default. Use Light Gray (#F8F5F2) or White (#FFFFFF) sparingly for content-heavy data slides.
- **Logo (cover)**: White Imgix logo, top-right of right panel (see Cover Slide spec).
- **Logo (non-cover slides)**: **Medium Gray (#BCB9B6)** Imgix logo, bottom-left corner, **20% smaller** than the cover logo. Respect the exclusion zone (height of the "x" in the wordmark). Minimum size: 100px / 0.75in for full logo, 40px / 0.5in for symbol only.
- **Page number**: Bottom-right, Caption size, Dark Gray (#807D7A) text.
- **The Beam**: Thin gradient bar along the bottom edge (see Beam section below).
- **Margins**: **60px (0.625")** on content slides; **80px (0.833")** on cover slides. Content should breathe — Imgix's aesthetic is spacious and clean.
- **Content-to-image gap**: **72px (0.75")** between left text content and right-side images/cards on content slides.

### Slide Types

**Title / Cover Slide**
- Split layout: Right panel is always **square** (7.5" × 7.5"), hero image fills remaining width
- **Vertical Beam** between image and right panel (gradient top-to-bottom: blue→green→cream→yellow→red)
- Left panel: Abstract blurred photo with brand color gradient treatment (blues, greens, oranges/reds)
- Right panel top-left: "IMGIX.COM" subhead (ALL CAPS, tracked, Mid Gray)
- Right panel top-right: Imgix logo (white) — **horizontally aligned** with IMGIX.COM text
- Right panel: Date in Mid Gray above title; gap between date and title = x-height of the title font (≈0.52 × em size)
- Right panel bottom: Large hero title in White, **Book weight** (bold:false), 44-48pt; title bottom sits 80px from slide bottom
- All right-panel content respects 80px margins on all four sides
- Page number bottom-right within right panel

**Section Divider**
- Off-Black background
- Section title in Hero size, positioned lower-right or center
- Large semi-transparent section number as background graphic element
- The Beam along bottom

**Content Slide (Text + 1 Screenshot)**
- Off-Black background (default) or Light Gray for data-dense slides
- Headline at top-left (28-36pt, Medium weight) — **no subhead above the headline**
- Body text / bullets below headline on the left (12px, Book weight, 140% line height, Mid Gray #BCB9B6); start body text **32px below** the headline bottom
- Single screenshot on the right with 36px padding + 24px border radius
- 72px gap between text content and screenshot
- Bullet style: simple round bullets; keep to 3-5 per slide max

**Content Slide (Text + 2 Landscape Screenshots)**
- Same left-side layout as above (headline + bullets)
- Two screenshots **stacked vertically** on the right, both the **same width**
- Each screenshot preserves its **native aspect ratio** — heights will differ
- 0.25" gap between the two screenshots
- Scale both proportionally if combined height exceeds usable area

**Content Slide (Text + 2 Portrait Screenshots)**
- Same left-side layout (headline + bullets)
- Two screenshots placed **side by side** on the right, both the **same height**
- Each screenshot preserves its **native aspect ratio** — widths will differ
- 0.2" gap between the two screenshots
- Right-align the pair within the right column area

**Content Slide (3 Screenshots + Bullets — 3-Column Layout)**
- Full-width layout (not split left/right)
- Headline at top-left spanning full width
- Three equal-width columns below, each containing:
  - Screenshot at top (same width, native AR, centered in column)
  - ALL CAPS subhead label below the screenshot
  - 3 bullet points below the label
- Equal gaps between columns

**Content Slide (4 Screenshots + Bullets — Single Row)**
- Full-width layout
- Headline at top-left spanning full width
- Four equal-width columns in a **single row** below, each containing:
  - Screenshot at top (same width, native AR, centered in column)
  - ALL CAPS subhead label below the screenshot
  - 3 bullet points below the label
- Equal gaps between columns (same as 3-column layout)

**Content Slide (Text + 4 Screenshots, No Bullets)**
- Headline + large paragraph on the left (~45%)
- Four screenshots in a **2×2 grid** on the right (~55%), filling the right area
- Each screenshot preserves its native aspect ratio, centered within its grid cell
- No bullets or labels on the screenshots — they speak for themselves

**Content Slide (Text + Stats)**
- Same as Text + 1 Screenshot but replace the right-side image with vertically stacked stat cards
- Stat cards: rounded rectangle (#252529), large number in White/Green/Yellow, small label in Dark Gray

**Data / Screenshot Slide**
- Off-Black background
- Screenshot or UI image placed with proper padding and border radius (see Image Treatment)
- Supporting text alongside or below the image
- Tables: use Off-Black cells with White text; header row slightly differentiated with Dark Gray background or subtle border

**Bento Grid Slide (Multiple Images, No Companion Copy)**
- **When to use**: ONLY when there are more than 4 images that don't need per-image companion copy (bullets, labels, etc.). This is NOT a default layout — use standard content slide layouts for 1–4 images.
- **Layout options**:
  - **Right-side bento** (default): Headline + description on the left (72px gap to images), bento grid on the right side. Use this unless the grid's natural width is ≥ 2× its height.
  - **Full-width row bento**: Only if the bento grid area's width would be ≥ 2× its height. Headline above, full-width image grid below.
- **Margins**: 60px (0.625") from all slide edges for the bento image area, consistent with content slide margins.
- **Grid algorithm**:
  - Distribute images into 2–3 rows. Each row's images share the same height; widths are determined by each image's aspect ratio.
  - Minimum 2 images per row.
  - Try all possible image-to-row assignments (brute force for ≤8 images) and pick the layout that maximizes area coverage while keeping row heights balanced.
  - Row height formula: `rowHeight = (availWidth - (N-1) * gutter) / sum(aspectRatios)`
  - If total row heights + gutters exceed available height, scale all rows down proportionally.
  - Center rows horizontally and the grid vertically if there's leftover space.
- **Gutters**: Equal spacing between all rows and columns — default 0.125" (~12px). Gutter must be identical everywhere in the grid.
- **Corner radius**: Same radius on every cell (24px at output resolution, scaled with any upscale factor). Corners use OOXML roundRect with per-image adj values calculated as `adj = (radiusEMU / min(cx,cy)) * 100000`. This is spec-correct for Keynote and PowerPoint; Pitch may show slight radius variation on images with very different aspect ratios (a known Pitch deviation from the OOXML spec, not a bug in the deck).
- **Cropping rules**:
  - **Photos/illustrations**: Crop to fit cell's aspect ratio. Optimize crop position for the main focal point — bias vertical crops ~35% from top (to favor faces/subjects). Center crop horizontally.
  - **Screenshots of charts, graphs, or text-heavy content**: NEVER crop. These must preserve their original aspect ratio. Place them in the grid at their native AR even if it creates uneven cell sizes. Text and data visualizations must remain fully readable.
  - **How to detect**: If an image contains visible text, data tables, axis labels, chart legends, or UI elements with readable copy, treat it as a no-crop image.
- **No padding** on bento cells (unlike screenshot treatment). The corner radius is applied directly to the cropped/resized image.
- **Image editability**: Images are converted from p:pic to p:sp (shape) elements with blipFill in OOXML post-processing. This gives users drag handles to resize and reposition. Note that the .pptx format uses "stretch to fill" for shape image fills — if someone changes a cell's aspect ratio, they should use the app's crop/mask tool to refit the image.
- **Resolution**: Render cells at 4× display resolution (96 DPI × 4 = 384 DPI) for sharp output on high-DPI screens.

**Closing / CTA Slide**
- Off-Black background
- Large hero statement
- Imgix logo prominent
- The Beam along bottom
- Optional: website URL in Subhead style (ALL CAPS, tracked)

---

## Image Treatment (Screenshots & UI)

This is critical for making rough screenshots look polished. When someone drops in a screenshot or UI image:

### Padding & Border Radius

Apply these treatments to every screenshot or UI image:

- **36px padding** around the screenshot on all sides
- **24px border radius** on the image corners
- **Padding color must match the screenshot's own main background color** (e.g., white padding for a white-background screenshot, dark padding for a dark-background screenshot)
- At 96 DPI, 36px = 0.375" in pptxgenjs coordinates
- Do NOT place screenshots on a separate background fill-color shape — bake the padding and radius into the image itself
- **Trim outer whitespace** from screenshots before adding padding.
- **Remove all borders**: Strip any thin solid-color borders from screenshot edges via multi-pass trim. The padding area must be completely clean — no border artifacts between content and padding.

### Screenshot Presentation Rules — CRITICAL
- **NEVER stretch a screenshot.** Always preserve the native aspect ratio. Scale uniformly to fit the available space.
- **NEVER change the styling of a screenshot** beyond padding + border radius. No recoloring, no theme changes, no overlays.
- **Upscale screenshots for maximum resolution** (4x with lanczos3 interpolation). This is purely a resolution improvement — content stays identical, just sharper on high-DPI displays.
- Multiple screenshots on one slide should have identical padding and radius treatment, but each maintains its own aspect ratio.
- When stacking screenshots vertically, calculate heights from each image's native aspect ratio — do not force equal heights.
- Screenshots can be skeuomorphic (showing browser chrome, app frames) — the brand allows this.

---

## The Beam

The Beam is Imgix's signature brand element — a thin gradient-filled horizontal bar.

### Gradient Specification (Light Gradient — use this for slides)

The Light Gradient flows left-to-right with these color stops:
- 0%: Blue (#207593)
- 25%: Green (#59BB91)
- 45%: Cream (#FFEABB)
- 75%: Yellow (#FFB824)
- 100%: Red (#FF3C00)

### Beam Rules
- Place along the **bottom edge** of every slide, spanning the full width
- Height should be < 5% of the slide height (roughly 0.25" or ~18px on a standard 7.5" tall slide)
- The gradient's red end should be on the **right** by default
- **Solid** beam (continuous gradient) is the default. Stepped beam (segmented rectangles) is an alternative.
- Only ONE beam per slide
- The beam must touch the slide edge on both short sides (bleed to edges)
- Never angle the beam
- Never use the gradient as a fill for other shapes
- Never place the beam alongside blurs
- Align the beam to the composition edge or along a major layout element (like the bottom of an image)

### Implementation
When building with pptxgenjs, create the beam as a rectangle shape spanning the full slide width, positioned at the very bottom, filled with a linear gradient using the color stops above.

---

## Logo Usage

- Use the **white logo** on Off-Black and dark backgrounds
- Use the **black logo** on Light Gray and white backgrounds
- The gradient logo (with Light Gradient applied to the symbol, white wordmark) is reserved for limited use: only on Off-Black backgrounds, with no other gradients in the composition, in sparse layouts
- **Exclusion zone**: equal to the height of the "x" in the wordmark — no text or elements within this zone
- **Minimum size**: Full logo 0.75in / 100px; Symbol only 0.5in / 40px
- Never alter, modify, or redraw the logo
- Place the logo consistently in the same position across all slides (bottom-left recommended for internal decks, per the sales deck template)

---

## Bullet Point & List Formatting

When content includes bullet points:

- Use simple round bullet characters
- **Bullet dot color: Dark Gray (#807D7A)** — not the same color as the text
- Body weight (Book / Medium in Plus Jakarta Sans), 12-14pt
- Line height: 140%
- Left-aligned, never centered
- Maximum 5 bullets per slide; if more content is needed, split across slides
- Indent sub-bullets by 0.3"
- Bullet text color: White (#FFFFFF) or Light Gray (#F8F5F2) on dark backgrounds; Off-Black on light backgrounds
- Space between bullets: 0.15-0.2" (enough to breathe but not so much it feels sparse)

---

## Tables

For data tables on slides:

- Header row: Dark Gray (#807D7A) background with White text, Medium weight
- Data rows: Off-Black (#1E1E23) background with White or Light Gray text, Book weight
- Alternating rows: subtle differentiation (e.g., #1E1E23 and #252529)
- Cell padding: comfortable (at least 8px vertical, 12px horizontal)
- Borders: thin (0.5-1pt), Mid Gray (#BCB9B6) or Dark Gray
- Number columns: right-aligned
- Text columns: left-aligned
- Highlight cells (e.g., key metrics): use Yellow (#FFB824) text sparingly

---

## What NOT to Do

These are common mistakes that break the brand:

1. **Don't use bright/saturated background colors** — Off-Black is the default, Light Gray for content-heavy exceptions only
2. **Don't use colors outside the palette** — no random blues, purples, or off-brand greens
3. **Don't adjust color transparency** — use the colors at full opacity
4. **Don't skip The Beam** — it should appear on every slide along the bottom
5. **Don't use multiple beams** on one slide
6. **Don't place raw, unpadded screenshots** — always apply the frame treatment with consistent padding and border radius
7. **Don't use centered body text** — left-align paragraphs and bullets
8. **Don't overcrowd slides** — Imgix's aesthetic is spacious and minimal; when in doubt, use fewer elements
9. **Don't forget the logo** — it should appear consistently (bottom-left) on all slides
10. **Don't use fonts other than Circular or Plus Jakarta Sans**
11. **Don't use low-contrast text** — especially avoid Mid Gray text on Off-Black backgrounds; stick to White or Light Gray for readability

---

## Quick Reference: Building a Deck

1. Read the `pptx` skill and follow its technical guidance for creating .pptx files (use pptxgenjs for from-scratch creation)
2. Set slide dimensions to 16:9 (13.33" x 7.5")
3. Default background: Off-Black (#1E1E23)
4. Add The Beam to every slide (gradient bar, full width, bottom edge)
5. Add Imgix logo to every slide (white, bottom-left, respecting exclusion zone)
6. Add page numbers (bottom-right, Dark Gray, Caption size)
7. Use Plus Jakarta Sans (or Circular if available) for all text
8. Apply the type hierarchy: Hero for impact statements, Headline for slide titles, Subhead (ALL CAPS) for labels, Body for content, Caption for footnotes
9. Wrap all screenshots/images in padded frames with proper border radius
10. Run QA per the pptx skill's QA instructions
