# Design System Specification: The Neon Muse

## 1. Overview & Creative North Star
### Creative North Star: "Hyper-Luxe Digital Play"
This design system moves away from the sterile, utilitarian nature of traditional note-taking apps. It embraces a "Hyper-Luxe Digital Play" aesthetic—an editorial fusion of Gen Z's vibrant energy and the sophisticated layering of high-end digital craftsmanship. 

We are not building a grid of boxes; we are creating a fluid, immersive workspace. The experience is defined by **intentional asymmetry**, where floating glass elements overlap to create a sense of tactile depth. By leveraging high-contrast typography scales against deep, "infinite" dark backgrounds, we ensure the interface feels like a premium fashion editorial rather than a standard SaaS tool.

---

## 2. Colors & Surface Logic
The palette balances high-octane neon accents with deep, light-absorbing dark tones to create a canvas where content literally glows.

### The "No-Line" Rule
**Explicit Instruction:** Designers are prohibited from using 1px solid borders for sectioning or containment. 
Boundaries must be defined through:
1.  **Tonal Shifts:** Placing a `surface_container_low` card on a `surface` background.
2.  **Luminous Softness:** Using the `outline_variant` at 10% opacity only when absolutely necessary.
3.  **Glow-Proximity:** Using a faint outer glow (`primary_dim` at 5% spread) to define an active area.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers—like stacked sheets of frosted neon glass.
*   **Base:** `surface` (#0e0e0e) – The infinite void.
*   **Sectioning:** `surface_container_low` (#131313) – Large layout blocks.
*   **Interactive Cards:** `surface_container_high` (#201f1f) – Individual note items.
*   **Overlays/Modals:** `surface_bright` (#2c2c2c) – Floating high-priority elements.

### The "Glass & Gradient" Rule
To achieve the "Hyper-Luxe" feel, main CTAs and "Hero" notes must utilize linear gradients.
*   **Signature Gradient:** `primary` (#db90ff) to `primary_container` (#d37bff) at a 135-degree angle.
*   **Glassmorphism:** For floating sidebars or toolbars, use `surface_variant` at 60% opacity with a `24px` backdrop-blur.

---

## 3. Typography
We utilize a triple-font strategy to create an editorial hierarchy that feels both trendy and authoritative.

*   **Display & Headlines (Plus Jakarta Sans):** Used for large, expressive titles. It provides a geometric, modern "fashion-tech" vibe.
    *   *Role:* Sets the mood. Use `display-lg` for empty states and `headline-md` for folder titles.
*   **Interface & Titles (Inter):** Used for functional UI elements and note titles. 
    *   *Role:* Clarity. Inter’s tall x-height ensures readability even when nested inside vibrant pastel cards.
*   **Labels (Be Vietnam Pro):** Used for metadata, tags, and micro-copy. 
    *   *Role:* Utility. Its slightly wider character tracking adds a "pro" technical feel to the playful UI.

**Typography as Brand:** Encourage extreme scale contrast. Pair a `display-lg` header with a `body-sm` metadata label to create a sophisticated, asymmetrical layout.

---

## 4. Elevation & Depth
Depth in this system is achieved through **Tonal Layering** and **Luminous Shadows**.

### The Layering Principle
Do not use shadows to separate a card from a list. Instead, use background color steps. A `surface_container_highest` note card should sit on a `surface_container` list view. This creates a soft, natural lift.

### Ambient Shadows & Glows
When an element must "float" (like a FAB or a Modal):
*   **Shadow:** 0px 20px 40px rgba(0, 0, 0, 0.4).
*   **Outer Glow:** Add a secondary shadow: 0px 0px 15px `surface_tint` at 15% opacity. This mimics the way neon light interacts with a dark surface.

### The "Ghost Border" Fallback
If a divider is required for accessibility, use the `outline_variant` (#484847) at **15% opacity**. Never use 100% solid lines.

---

## 5. Components

### Note Cards (The Signature Element)
*   **Background:** Use pastel tokens (`secondary_fixed`, `tertiary_fixed`) at 15% opacity over `surface_container_high`.
*   **Corners:** Use the `xl` (3rem / 48px) radius for the outer container and `lg` (2rem / 32px) for internal elements.
*   **State:** On hover, scale the card by 1.02x and increase the `backdrop-blur`.

### Buttons
*   **Primary:** A vibrant `primary` (#db90ff) fill. Text color: `on_primary`. Shape: `full` (pill).
*   **Secondary (Glass):** `surface_variant` at 40% opacity with a `20%` `outline` ghost border.
*   **Interaction:** Smooth 300ms cubic-bezier transitions on all hover states. Add a subtle "glow" on hover using the `primary_dim` token.

### Input Fields
*   **Styling:** No background. Use a `surface_container_highest` bottom-only "thick" underline (4px) that transitions to `primary` when focused.
*   **Focus State:** The cursor/caret should be `tertiary` (#aaffdc) to provide a "pop" of color against the dark text.

### Selection Chips
*   **Style:** `full` (pill) radius.
*   **Unselected:** `surface_container_highest` background.
*   **Selected:** `secondary` (#ff67b1) with an `on_secondary` text label. 

---

## 6. Do’s and Don’ts

### Do
*   **DO** use emojis as functional icons. A 🍋 emoji is more "on-brand" for a lemon-yellow note than a standard folder icon.
*   **DO** leave massive amounts of white space (or "dark space"). The `xl` spacing token is your friend.
*   **DO** overlap elements. Let a glass-toolbar partially obscure a note card to create depth.

### Don't
*   **DON'T** use pure black (#000000) for anything except the `surface_container_lowest`. Use the rich `surface` (#0e0e0e) to maintain tonal depth.
*   **DON'T** use 90-degree corners. Everything must feel soft, organic, and approachable.
*   **DON'T** use standard grey shadows. If a card is "Electric Purple," its shadow should have a hint of purple tint.