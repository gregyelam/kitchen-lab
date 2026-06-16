# Design System Document: High-Contrast Neo-Brutalism

## 1. Overview & Creative North Star: "The Raw Kitchen"
This design system rejects the polished, overly-sanitized aesthetic of modern lifestyle apps in favor of a "Raw & Energetic" editorial approach. The Creative North Star is **The Digital Fanzine**: a high-impact, anti-fancy interface that feels like a premium street-culture magazine. 

We break the "template" look by utilizing intentional asymmetry, aggressive typography scales, and overlapping elements. This system is designed to feel alive—mimicking the chaotic, vibrant energy of a professional kitchen where the food is messy, the heat is high, and the focus is on the soul of the dish rather than the perfection of the plating.

## 2. Colors & Surface Logic
The palette is built on extreme contrast. We use a "Stark" foundation punctuated by a hyper-vibrant neon green to signal action and energy.

### Core Palette
- **Primary / Action:** `primary` (#0f6b00) & `primary_fixed` (#2ff801). Use the Neon Green (`primary_fixed`) for high-energy interactions.
- **Surface:** `surface` (#f6f6f6) and `surface_container_lowest` (#ffffff).
- **On-Surface:** `on_surface` (#2d2f2f) for primary text; `on_background` (#2d2f2f) for heavy headings.
- **Accents:** `tertiary` (#0846ed) Electric Blue for secondary highlights or informational callouts.

### The "No-Line" Rule (For Sectioning)
Standard 1px hairline dividers are strictly prohibited. To define sections, use:
1.  **Background Color Shifts:** Transition from `surface` to `surface_container_low` (#f0f1f1).
2.  **Structural Borders:** If a boundary is needed, it must be an intentional "Neo-Brutalist" stroke (2px to 4px) using `on_background`. 

### Surface Hierarchy & Nesting
Treat the UI as a series of physical, stacked layers. 
- **Base Layer:** `surface` (#f6f6f6).
- **Content Cards:** `surface_container_lowest` (#ffffff) to provide a crisp lift.
- **Nested Detail:** `surface_container` (#e7e8e8) for internal groupings within a card.

### The "Glass & Gradient" Rule
To elevate the "Raw" aesthetic into a "Premium" space, use **Glassmorphism** for floating elements (e.g., navigation bars or recipe filters). Apply `surface_container_lowest` at 60% opacity with a `20px` backdrop blur. For primary CTAs, use a subtle gradient from `primary` (#0f6b00) to `primary_fixed` (#2ff801) to add depth.

## 3. Typography: Aggressive Editorial
Our typography is a clash between industrial utility and classic editorial charm.

- **Display & Headlines (`spaceGrotesk`):** Use for recipe titles and bold statements. It should feel loud and unapologetic. 
    - *Note:* Use `display-lg` (3.5rem) for hero titles to command attention.
- **Body & Titles (`newsreader`):** A clean, high-end serif that mimics food journalism. Use for ingredient lists and cooking steps.
    - *Note:* The serif adds a "chef’s notes" feeling, providing a human touch to the brutalist layout.
- **Labels (`spaceGrotesk`):** Use for technical data (e.g., "15 MINS," "EASY") in all-caps to maintain the fanzine aesthetic.

## 4. Elevation & Depth: Tonal & Physical Layering
We do not use standard Material Design shadows. We achieve depth through "Structural Brutalism."

- **The Layering Principle:** Stack `surface-container` tiers. A `surface-container-lowest` card sitting on a `surface-container-high` background creates a "natural" lift.
- **The "Ghost Border" Fallback:** If a 4px black border is too heavy for a specific sub-element, use a "Ghost Border"—the `outline_variant` token at 20% opacity. 
- **Zero Rounding:** All containers must use a `0px` radius. Sharp corners are non-negotiable to maintain the aggressive, raw edge.
- **Ambient Shadows:** Only for floating action buttons or modal overlays. Use the `on_surface` color at 8% opacity with a massive 40px blur—creating a "smudge" rather than a "shadow."

## 5. Components

### Buttons
- **Primary:** `primary_fixed` background, `on_primary_fixed` text, 4px black border (`on_background`). Sharp corners.
- **Secondary:** `surface` background, 2px black border.
- **State Change:** On hover/active, shift the background color to `primary_dim` or invert the colors entirely.

### Input Fields
- **Styling:** `surface_container_lowest` background, 2px solid `on_background` border. 
- **Focus State:** Increase border to 4px and use `primary_fixed` as a subtle "glow" underneath the border.

### Cards & Lists
- **Forbid Dividers:** Use `1.4rem` (`spacing-4`) of vertical whitespace or a shift to `surface_container_low` to separate items.
- **Visual Style:** Large, raw photography should fill the top 60% of cards, with text overlapping the image using a glassmorphic label.

### Recipe "Step" Chips
- **Styling:** Small, rectangular blocks with `surface_dim` backgrounds and `label-md` typography. Use these for difficulty levels or nutritional tags.

## 6. Do's and Don'ts

### Do:
- **Use Raw Imagery:** Photography should show spills, steam, and half-eaten plates. Avoid sterile, white-background "stock" photos.
- **Embrace Asymmetry:** Offset headings or let images bleed off the edge of the screen to create energy.
- **Use Spacing Scale:** Stick strictly to the spacing scale (e.g., `8.5rem` for section breaks) to ensure the "messy" look is actually highly calculated.

### Don't:
- **No Rounded Corners:** Never use `border-radius`. Everything is a hard 90-degree angle.
- **No Thin Lines:** Avoid 1px lines. They feel "fragile," whereas the brand is "tough."
- **No Pastel Colors:** Stick to the high-contrast tokens. If it's not Stark Black, Pure White, or Neon Green, it shouldn't be a primary interface element.
- **No Smooth Transitions:** Micro-interactions should be "snappy" (0.1s or 0s duration). Elements should snap into place, not slide.

## 7. Imagery Guidelines
Images are the "soul" of this system. 
- **Style:** High saturation, hard shadows (top-down lighting), and "dirty" compositions (flour on the counter, oil splatters).
- **Integration:** Use a `2px` black stroke around all image containers to "frame" them like a printed photograph.