# Design System Strategy: The Northwoods Editorial

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Digital Outpost."** We are moving away from the cluttered, utilitarian "bait shop" aesthetic and toward a high-end, editorial experience that feels like a premium field guide. 

This design system rejects the rigid, boxy constraints of traditional e-commerce. Instead, it embraces **intentional asymmetry**, **tonal layering**, and **expansive whitespace** to evoke the feeling of the great outdoors. We achieve a "Modern Northwoods" feel by pairing rugged, rustic serif typography with a sophisticated, organic color palette. The goal is to establish a sense of local expertise and quiet confidence—quality gear, expertly curated, presented with breathable elegance.

---

2. Colors: Tonal Depth vs. Structural Lines
Our palette is rooted in the forest floor and lake-edge stones. We do not use borders to define space; we use light and earth.

### The "No-Line" Rule
Explicitly prohibit 1px solid borders for sectioning. Structural boundaries must be defined solely through background color shifts. For example, a `surface-container-low` section should sit directly against a `background` or `surface` area. The transition between #fff8f4 and #fff1e4 is your "line."

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers—stacked sheets of fine, heavy-weight paper.
*   **The Base:** `background` (#fff8f4) or `surface-container-low` (#fff1e4).
*   **The Feature:** Use `surface-container-highest` (#f8dec1) for featured product carousels to create a "warm wood" focal point.
*   **The Inset:** Use `surface-dim` (#efd6b9) for utility areas like filters or footers to provide a grounded, "slate" feel.

### The "Glass & Gradient" Rule
To prevent the UI from feeling "flat" or "muddy," use Glassmorphism for floating navigation bars or over-image labels. 
*   **Implementation:** Use `surface` colors at 80% opacity with a `20px` backdrop-blur. 
*   **Signature Textures:** Apply a subtle linear gradient from `primary` (#004b00) to `primary-container` (#006600) on main CTAs to mimic the depth of a pine canopy.

---

3. Typography: The Rugged Intellectual
We utilize a high-contrast pairing of `newsreader` (a rustic, authoritative serif) and `publicSans` (a clean, utilitarian sans-serif).

*   **Display & Headline (`newsreader`):** These are our "Editorial Voices." Use these for hero statements and category titles. The serif nature conveys history and local expertise.
*   **Title & Body (`publicSans`):** These are our "Functional Voices." Used for product names, descriptions, and technical specs. The sans-serif clarity ensures high readability on mobile.
*   **The "Field Note" Style:** Use `label-md` in all-caps with a `0.05rem` letter-spacing for category tags, mimicking the look of stamped gear crates.

---

4. Elevation & Depth: Tonal Layering
Traditional shadows and borders are too "tech." We prefer **Ambient Depth.**

*   **The Layering Principle:** Place a `surface-container-lowest` card on a `surface-container-low` section. This creates a soft, natural "lift" that mimics paper resting on a wooden table.
*   **Ambient Shadows:** If a floating element (like a "Quick Shop" modal) requires a shadow, it must use the `on-surface` color (#261907) at 5% opacity with a `32px` blur and `8px` Y-offset. It should feel like a soft glow, not a hard drop.
*   **Ghost Border Fallback:** If accessibility requires a border (e.g., input fields), use `outline-variant` (#bfcab7) at **15% opacity**. It should be a suggestion of a boundary, not a cage.

---

5. Components

### Buttons
*   **Primary:** Background: `primary` (#004b00); Text: `on-primary` (#ffffff). Shape: `md` (0.375rem). No shadow.
*   **Secondary:** Background: `secondary` (#934b19); Text: `on-secondary`. Use for "Add to Cart" to provide a warm, "leather-tone" contrast.
*   **Tertiary:** Transparent background with `newsreader` bold text and a `primary` underline (2px) that appears on hover.

### Cards & Lists
*   **The Rule:** No dividers. Use `2rem` to `3rem` of vertical whitespace to separate list items.
*   **Card Style:** Use `surface-container-lowest` (#ffffff) with a `lg` (0.5rem) corner radius. Use tonal shifts to highlight a "hover" state rather than an outline.

### Input Fields
*   **Surface:** `surface-container-lowest`.
*   **Indicator:** Instead of a full-box border, use a 2px bottom-border of `primary` only when the field is focused. This keeps the form feeling open and airy.

### Signature Component: "The Compass Chip"
Use for filtering (e.g., "Fishing," "Hunting"). 
*   **Style:** `surface-variant` background, `publicSans` Semi-bold text. When selected, shift to `primary` with `on-primary` text. The shape should be `full` (pill-shaped) to contrast the rugged typography.

---

6. Do's and Don'ts

### Do:
*   **Embrace Asymmetry:** In hero sections, offset text to the left and imagery to the right with overlapping elements to create an editorial feel.
*   **Use High-Quality Imagery:** Use photos with deep shadows, natural light, and "outdoors-in-action" subjects.
*   **Prioritize Breathing Room:** If a layout feels crowded, increase the spacing by 50%. The "Northwoods" is about vast spaces.

### Don't:
*   **Don't use pure black:** Use `on-background` (#261907) for text to maintain a warm, organic feel.
*   **Don't use "Full-Bleed" Dividers:** Never use a horizontal line that spans the screen. It breaks the organic flow of the "Digital Outpost."
*   **Don't over-round corners:** Stick to `sm` or `md` for functional elements. `full` rounding is only for chips. We want the UI to feel "hand-crafted," not "bubbly."

### Accessibility Note:
Ensure the contrast between `on-surface-variant` (#404a3b) and `surface` (#fff8f4) meets WCAG AA standards for secondary text. If the green-grey is too light on specific displays, default to `on-surface`.