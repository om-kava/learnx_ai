```markdown
# Design System Document: The Editorial Intelligence Framework

## 1. Overview & Creative North Star
**Creative North Star: "The Digital Curator"**

This design system rejects the "standard SaaS dashboard" in favor of a high-end, editorial experience. It is designed for an AI-powered learning environment where focus is a premium commodity. By combining the precision of fintech aesthetics with the grace of modern typography, we move away from "software" and toward "experience."

To break the template look, this system utilizes **Intentional Asymmetry**. We do not align everything to a rigid 12-column center. Instead, we use expansive negative space (using the `20` and `24` spacing tokens) to pull the eye toward focal points. Overlapping elements—such as glass cards bleeding off the edge of a container—create a sense of depth and motion, making the UI feel alive and sophisticated rather than static.

---

## 2. Colors & Surface Philosophy
The palette is rooted in the depth of midnight, utilizing a "Dark Pro" aesthetic that prioritizes eye comfort and premium feel.

### The "No-Line" Rule
**Explicit Instruction:** Designers are prohibited from using 1px solid borders for sectioning or layout containment. 
Boundaries must be defined solely through background color shifts. For example, a sidebar should be `surface_container_low` sitting against a `background` viewport. The human eye is sophisticated enough to perceive these tonal shifts without the "crutch" of a stroke.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers—stacked sheets of obsidian and frosted glass.
*   **Base:** `background` (#111318) for the main application canvas.
*   **Level 1:** `surface_container_low` for large structural areas (e.g., a content feed).
*   **Level 2:** `surface_container` for secondary modules.
*   **Level 3:** `surface_container_highest` for active, interactive elements like popovers or modals.

### The "Glass & Gradient" Rule
To inject "soul" into the dark UI, use **Glassmorphism** for floating elements. 
*   **Formula:** `surface_variant` at 40% opacity + `backdrop-blur: 24px`. 
*   **Gradients:** Use a transition from `primary_container` (#1032CF) to `secondary_container` (#CA04B7) at a 135-degree angle for hero CTAs and primary progress indicators. This provides a "neon glow" that feels electric yet professional.

---

## 3. Typography
We use a high-contrast typographic scale to establish authority and elegance.

*   **Display & Headlines (Manrope):** Chosen for its geometric modernism. Use `display-lg` and `headline-lg` with tight letter-spacing (-0.02em) to create a "bold editorial" look.
*   **Body & Titles (Inter):** The workhorse of readability. Inter’s tall x-height ensures clarity against dark backgrounds. Use `body-md` for standard text and `title-sm` for navigation labels.
*   **Hierarchy Note:** Always maintain a minimum 2-step jump in the scale for adjacent elements (e.g., a `headline-sm` should be followed by `body-md`, skipping `title-lg`) to ensure the hierarchy is unmistakable.

---

## 4. Elevation & Depth
Depth is achieved through **Tonal Layering**, not structural lines.

*   **The Layering Principle:** Place a `surface_container_lowest` card on a `surface_container_low` section to create a soft, natural lift. This "recessed" look feels more premium than a simple drop shadow.
*   **Ambient Shadows:** For floating elements (modals, dropdowns), use extra-diffused shadows.
    *   **Value:** `0px 24px 48px -12px rgba(0, 0, 0, 0.5)`. The shadow must feel like a soft atmospheric occlusion, not a hard "drop."
*   **The "Ghost Border" Fallback:** If accessibility requirements demand a border, use `outline_variant` at **15% opacity**. High-contrast borders are strictly forbidden as they break the "glass" illusion.

---

## 5. Components

### Buttons
*   **Primary:** A gradient fill (`primary_container` to `secondary_container`). `xl` roundedness (3rem). No border.
*   **Secondary:** `surface_container_high` background with `on_surface` text. 
*   **States:** On hover, primary buttons should trigger a `secondary` glow effect (box-shadow using the `secondary` token at 20% opacity).

### Cards & Modules
*   **Rule:** Forbid divider lines. Separate content using the `spacing-6` (2rem) or `spacing-8` (2.75rem) tokens. 
*   **Style:** `lg` roundedness (2rem). Use `surface_container` for static cards and Glassmorphism (blur) for interactive cards.

### Input Fields
*   **Style:** Minimalist. No bottom line or full box. Use a `surface_container_highest` background with `sm` roundedness. 
*   **Focus State:** A subtle glow using `tertiary` (#00DAF3) at 10% opacity, rather than a hard stroke.

### AI Learning Specifics: "The Focus Path"
*   **Progress Orbs:** Instead of standard bars, use glowing circular rings with a `primary` to `tertiary` gradient.
*   **AI Insight Chips:** Use the `tertiary_container` with a high `backdrop-blur` to signify "AI-generated" content, distinguishing it from static student data.

---

## 6. Do’s and Don'ts

### Do:
*   **Use breathing room:** If you think a section needs more space, use the next size up in the spacing scale.
*   **Layer logically:** Always move from darker (`surface_dim`) to lighter (`surface_bright`) as you move "closer" to the user.
*   **Subtle Animation:** Use `ease-in-out` transitions (300ms) for all hover states. Gradients should subtly shift their angle on hover.

### Don’t:
*   **Don't use pure white text:** Use `on_surface_variant` (#C5C5D8) for body text to reduce eye strain and maintain the "pro" feel. Reserve pure white for Headlines.
*   **Don't use 1px borders:** Ever. If you feel the need to separate, use a background color shift.
*   **Don't clutter:** Every element on the screen must serve a functional or emotional purpose. If it does neither, remove it.