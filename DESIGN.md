# Design System Strategy: The Sovereign Ledger

## 1. Overview & Creative North Star
The "Sovereign Ledger" is the creative North Star of this design system. It moves away from the clinical, cold aesthetic of traditional legal tech and toward the warmth and authority of a premium editorial publication. The goal is to evoke the feeling of a heavy, leather-bound volume translated into a high-performance digital interface.

We break the "template" look through **intentional asymmetry** and **tonal depth**. The design system favors wide margins, oversized serif headings, and a layout that feels "curated" rather than "generated." By utilizing a high-contrast typography scale and layered surfaces, we establish a visual hierarchy that feels both unshakable and sophisticated.

---

## 2. Colors & Surface Philosophy
The palette is rooted in a deep, verdant foundation, using `#29A560` as the primary engine. In a dark mode context, this provides a "luminescent ink" effect against the `surface` (`#121412`).

### The "No-Line" Rule
**Explicit Instruction:** All designers are prohibited from using 1px solid borders to define sections. Layout boundaries must be established exclusively through background color shifts. A `surface-container-low` section sitting on a `surface` background is the only acceptable way to denote a change in content context.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers—like stacked sheets of fine, heavy-weight paper.
*   **Base:** `surface` (#121412)
*   **Low Importance/Background:** `surface-container-low` (#1a1c1a)
*   **Standard Cards/Modules:** `surface-container` (#1e201e)
*   **Prominent Interaction Points:** `surface-container-high` (#282a28)

### The "Glass & Gradient" Rule
To escape the "flat" look of standard Material UI, floating elements (modals, dropdowns) should utilize **Glassmorphism**. Use semi-transparent `surface-container` colors with a `backdrop-blur` (minimum 12px). 

**Signature Texture:** Main CTAs and Hero sections should utilize a subtle linear gradient (135°) transitioning from `primary` (#69dd91) to `primary_container` (#29A560). This adds "soul" and a sense of premium materiality that flat hex codes cannot provide.

---

## 3. Typography
The typography is a dialogue between the tradition of the law (**Newsreader**) and the precision of modern commerce (**Manrope**).

*   **Display & Headlines (Newsreader):** Use `display-lg` through `headline-sm` for all high-level messaging. The variable weight of Newsreader should be used to create an "Editorial" feel—large, bold headlines that demand attention and convey authority.
*   **Titles & Body (Manrope):** `title-lg` down to `body-sm` utilize Manrope. This sans-serif provides a functional, utilitarian contrast to the serif headings, ensuring that complex legal data remains legible and modern.
*   **Labels (Manrope):** `label-md` and `label-sm` are for metadata and micro-copy, acting as the "fine print" that is nonetheless crystalline in its clarity.

---

## 4. Elevation & Depth
In the Sovereign Ledger, depth is achieved through **Tonal Layering** rather than structural lines.

*   **The Layering Principle:** Stack `surface-container` tiers to create lift. For example, place a `surface-container-lowest` card on a `surface-container-low` section. This creates a soft, natural depth that feels organic to the dark-mode environment.
*   **Ambient Shadows:** When an element must "float" (e.g., a primary action button), use an extra-diffused shadow. Shadow color must be a tinted version of `on_surface` at 4-8% opacity, never a generic black or grey.
*   **The Ghost Border:** If a boundary is strictly required for accessibility, use the `outline_variant` token at **10-20% opacity**. 100% opaque borders are strictly forbidden as they break the editorial flow.

---

## 5. Components

### Buttons
*   **Primary:** A gradient fill (`primary` to `primary_container`) with `on_primary_container` text. Use `md` (0.375rem) roundedness to maintain a professional, slightly sharp edge.
*   **Secondary:** `surface-container-high` fill with a "Ghost Border" of `primary` at 20% opacity.
*   **Tertiary:** Text-only using the `primary` token; no container.

### Cards & Lists
*   **Rule:** Forbid the use of divider lines. 
*   **Implementation:** Separate list items using vertical white space from the spacing scale (e.g., 1rem gaps) or by alternating subtle background shifts (`surface-container-low` vs `surface-container`).

### Input Fields
*   **Style:** Minimalist. No bottom line or full box. Use a `surface-container-highest` background with a `md` (0.375rem) corner radius.
*   **Focus State:** A soft `primary` glow (glow effect, not a harsh border).

### Sovereign Ledger Specific: The "Case File" Header
A custom component for this system. A large-scale `display-sm` Newsreader title paired with a `label-md` Manrope timestamp and a `primary` colored accent bar (2px thick, 24px wide) placed asymmetrically to the left.

---

## 6. Do's and Don'ts

### Do
*   **DO** use whitespace as a structural element. If a section feels crowded, increase the padding rather than adding a line.
*   **DO** use Newsreader for any text meant to sound "authoritative" or "final."
*   **DO** leverage `primary_fixed_dim` for subtle icons that need to feel integrated into the background.

### Don't
*   **DON'T** use 100% white (#FFFFFF). Always use `on_surface` (#e2e3df) to maintain the "aged paper" digital feel and reduce eye strain in dark mode.
*   **DON'T** use `full` (9999px) roundedness for buttons; it feels too "tech-startup" and undermines the law firm's authority. Stick to `md` or `lg`.
*   **DON'T** ever use a standard "drop shadow" preset. All shadows must be ambient and tinted.