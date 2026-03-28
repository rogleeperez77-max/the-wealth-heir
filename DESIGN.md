```markdown
# Design System Document: The Modern Prestige

## 1. Overview & Creative North Star
This design system is built to evoke the quiet confidence of an elite lifestyle. We are moving away from the cluttered, "conversion-at-all-costs" aesthetic of typical landing pages and toward a high-end editorial experience. 

**Creative North Star: "The Curated Legacy"**
The design must feel like a limited-edition physical publication. We achieve this through "The Curated Legacy" approach: utilizing extreme negative space, intentional asymmetry (e.g., staggering images and text blocks), and a typography-first hierarchy. Every element should feel like it was placed by hand on a canvas, not snapped into a rigid, predictable grid. We embrace the "Elite Lifestyle" by reflecting the textures of the reference image: the crispness of a linen shirt, the depth of a midnight blazer, and the sharp glint of gold hardware.

---

## 2. Colors
Our palette relies on a high-contrast relationship between deep, authoritative tones and luminous highlights.

*   **Primary Palette:** We use the deep midnight tones (`primary`, `primary_container`) to establish weight and authority.
*   **Secondary/Tertiary (Gold):** Gold accents (#D4AF37, mapped to `secondary` and `tertiary` tokens) must be used sparingly—like a bespoke watch or belt buckle. Use them only for high-intent CTAs or subtle "Seal of Quality" elements.
*   **Neutral (Off-White):** Our `surface` and `background` (#f9faf8) provide the "breathing room" required for a luxury feel.

### The "No-Line" Rule
Standard UI relies on borders to separate content. **In this design system, 1px solid borders are strictly prohibited for sectioning.** Boundaries must be defined through:
1.  **Background Color Shifts:** A section using `surface_container_low` sitting atop a `background` section.
2.  **Vertical White Space:** Use the `20` (7rem) or `24` (8.5rem) spacing tokens to create mental "chapters" in the scroll.

### Surface Hierarchy & Nesting
Treat the UI as physical layers. An author bio card should not just sit on the page; it should be a `surface_container_lowest` element nested within a `surface_container` section to create a soft, recessed depth.

### The "Glass & Gradient" Rule
To mimic the reflection of light on premium materials (yacht finishes, glass storefronts), use **Glassmorphism** for floating navigation or overlays. 
*   **Formula:** `surface` color at 70% opacity + `backdrop-blur` (20px-40px).
*   **Signature Textures:** Use subtle linear gradients from `primary` to `primary_container` (Midnight to Navy) for hero backgrounds to avoid a "flat" digital appearance.

---

## 3. Typography
Typography is the voice of the ebook. We pair the authoritative weight of a serif with the modern precision of a sans-serif.

*   **Headings (Noto Serif):** Used for all `display` and `headline` levels. This font carries the "Editorial" weight. Headlines should use `display-lg` with tight letter-spacing to feel like a magazine cover.
*   **Body (Manrope):** Used for `title`, `body`, and `label` levels. Manrope is modern and clean, ensuring that while the headings are "art," the information is "accessible."
*   **Hierarchy Note:** Always maintain a significant scale jump between your `headline-lg` and your `body-lg`. Luxury is expressed through the confidence of large, bold titles and generous leading (line-height) in the body text.

---

## 4. Elevation & Depth
We eschew the heavy shadows of the 2010s in favor of **Tonal Layering**.

*   **The Layering Principle:** Depth is achieved by "stacking" surface tokens. For example, a "Buy Now" card should be `surface_container_lowest` (pure white) placed on a `surface_container` (light grey/white) background. This creates a natural "lift" without visual noise.
*   **Ambient Shadows:** If a floating element (like a modal or floating CTA) requires a shadow, it must be an "Ambient Shadow." 
    *   **Spec:** 0px 20px 50px rgba(0, 0, 0, 0.04). It should be barely perceptible—a "felt" shadow rather than a "seen" one.
*   **The "Ghost Border" Fallback:** If a container requires a boundary (e.g., a text input), use the `outline_variant` token at **15% opacity**. It should appear as a faint suggestion of a shape.
*   **Glassmorphism Depth:** For floating "Lifestyle" callouts, use a semi-transparent `surface` with a heavy blur. This allows the midnight blue or gold accents of the background to bleed through, integrating the component into the environment.

---

## 5. Components

### Buttons
*   **Primary (Midnight):** `primary` background, `on_primary` text. Sharp, refined edges (`DEFAULT` 0.25rem). 
*   **Secondary (Gold Accent):** `secondary` background with `on_secondary` text. Reserved only for the primary conversion (e.g., "Download Ebook").
*   **States:** On hover, primary buttons should transition to a subtle gradient rather than a simple color change.

### Editorial Cards
*   **Rule:** Forbid the use of divider lines. 
*   **Style:** Use a combination of `title-lg` for names and `body-md` for descriptions. Group content using `spacing-6` (2rem) and allow the alignment (e.g., left-aligned text with a right-aligned image) to create the structure.

### Input Fields
*   **Style:** Minimalist. No background fill—only a bottom "Ghost Border" using `outline_variant` at 20% opacity. Labels should use `label-md` in `on_surface_variant`.

### Signature Component: The "Lifestyle Overlay"
A specialized component for this system: An image (`surface_variant` placeholder) with an overlapping text block. The text block should use Glassmorphism (semi-transparent `surface_container_lowest`) and be positioned asymmetrically (e.g., bottom-right of the image) to break the grid.

---

## 6. Do's and Don'ts

### Do:
*   **Embrace the Void:** Use the `24` (8.5rem) spacing token between major sections. If it feels like "too much" white space, it’s probably just right.
*   **Asymmetric Balance:** Place an image on the left and a text block slightly lower on the right. This creates a "scrolling journey" rather than a repetitive "checkerboard."
*   **Tonal Consistency:** Ensure your `on_surface` (Midnight) text is always legible against the `surface` (Off-white).

### Don't:
*   **Don't use 100% Black:** Use the `primary` midnight blue for text to maintain a "midnight/gold" sophistication. Pure black (#000000) is too harsh for an elite lifestyle aesthetic.
*   **Don't use Rounded Corners:** Avoid the `full` or `xl` roundedness tokens. High-end luxury is often associated with the precision of sharp or subtly softened edges (`DEFAULT` or `sm`).
*   **Don't Over-Animate:** Animations should be "slow and heavy." Use long durations (500ms+) with elegant easing (Cubic Bezier) for fade-ins. Avoid "bouncy" or "snappy" transitions.

### Accessibility Note:
While we use "Ghost Borders" and subtle tonal shifts, ensure that interactive elements (like inputs) have a high-contrast focus state using the `secondary` (Gold) token to meet WCAG standards without compromising the elite aesthetic.```