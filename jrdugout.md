# Design System Document

## 1. Overview & Creative North Star: "The Embers of Caracas"
This design system is built to evoke the sensory experience of a high-end Venezuelan grill: the heat of the *brasa*, the golden hue of toasted maize, and the sophisticated grit of charcoal.

**The Creative North Star: "The Embers of Caracas"**
We reject the "fast food" template. Our goal is **Editorial Gastronomy**. This means moving away from rigid, boxed grids and instead using intentional asymmetry, overlapping high-contrast photography with bold typography, and a depth-first approach to layering. The UI should feel like a premium culinary magazine—dynamic, smoky, and visceral.

---

## 2. Colors: Tonal Depth over Borders
The palette is rooted in the transition from raw coal to glowing flame. We use deep charcoal surfaces to make the vibrant oranges and yellows of the food and brand pop.

### The "No-Line" Rule
**Strict Mandate:** Designers are prohibited from using 1px solid borders to define sections or cards. Hierarchy must be established through background color shifts.
* **Example:** A `surface-container-low` section sitting on a `surface` background.
* **Why:** Lines create "visual noise" that feels cheap. Tonal shifts feel like architectural layers.

### Surface Hierarchy & Nesting
Use the `surface-container` tiers to create a "physical" stack.
* **Base Level:** `surface` (#131313) for the main viewport.
* **Section Level:** `surface-container-low` (#1B1C1C) to group menu categories.
* **Component Level:** `surface-container-high` (#2A2A2A) for active cards or floating modals.

### The "Glass & Gradient" Rule
To add "soul" to the interface, avoid flat #E65100 for large CTAs. Instead:
* **Signature Gradient:** Use a linear gradient from `primary` (#FFB59A) to `primary-container` (#F95E14) at a 135-degree angle. This mimics the flicker of a flame.
* **Glassmorphism:** For floating navigation or "Quick Add" bars, use `surface-container` at 70% opacity with a `20px` backdrop-blur. This keeps the juicy food photography visible beneath the UI.

---

## 3. Typography: The Editorial Voice
We use typography to command attention and guide the appetite.

* **The Display Choice (Epilogue):** This is our "Editorial" voice. It is heavy, grounded, and authoritative. Use `display-lg` for hero headlines that overlap food imagery.
* **The Utility Choice (Plus Jakarta Sans):** A sophisticated sans-serif that ensures legibility for ingredients and prices even at small sizes.

| Level | Token | Font | Size | Weight | Use Case |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Hero** | `display-lg` | Epilogue | 3.5rem | Bold | Main Menu Headings |
| **Section** | `headline-md` | Epilogue | 1.75rem | Bold | Category Titles (e.g., "Las Arepas") |
| **Product** | `title-lg` | Plus Jakarta | 1.375rem | Semi-Bold | Food Item Names |
| **Body** | `body-md` | Plus Jakarta | 0.875rem | Regular | Ingredient Descriptions |
| **Utility** | `label-md` | Plus Jakarta | 0.75rem | Medium | "Spicy" or "Gluten-Free" tags |

---

## 4. Elevation & Depth: Tonal Layering
Traditional shadows are often too "digital." We use **Ambient Layering** to create a premium feel.

* **The Layering Principle:** Instead of a shadow, place a `surface-container-highest` card on a `surface-container-low` background. The difference in luminosity creates a natural lift.
* **Ambient Shadows:** If a floating element (like a Cart FAB) requires a shadow, use a large blur (32px) at 8% opacity using the `on-surface` color. It should look like a soft glow, not a dark stain.
* **The Ghost Border Fallback:** If a container is placed on an identically colored background and requires definition, use the `outline-variant` token (#5A4138) at **15% opacity**. It should be felt, not seen.

---

## 5. Components: Tactile & Modern

### Buttons (The "Crave" Action)
* **Primary:** Gradient from `primary` to `primary-container`. `xl` (0.75rem) roundedness. No border.
* **Secondary:** `surface-container-highest` with `on-surface` text. For "Customize" or "View Details."
* **Haptic Feed:** On hover, the primary button should scale slightly (1.02x) and increase its `surface-tint` intensity.

### Cards & Lists (The Menu)
* **Forbid Dividers:** Do not use lines between menu items. Use `spacing-6` (2rem) of vertical whitespace or a subtle shift to `surface-container-low`.
* **Food Imagery:** Cards should be "Edge-to-Edge" on the top half. Use high-contrast photography where the meat texture is visible.
* **The "Maíz" Chip:** Selection chips use `secondary-container` (#FABD00) with `on-secondary-container` text. These highlight key modifiers (e.g., "Extra Queso").

### Input Fields
* **Style:** Filled, not outlined. Use `surface-container-highest`.
* **Focus State:** Transition the bottom 2px of the field to `primary` (#FFB59A).

---

## 6. Do's and Don'ts

### Do
* **Do** overlap text on images. Use a 40% black-to-transparent gradient overlay on images to ensure `on-background` text readability.
* **Do** use the `spacing-16` and `spacing-20` for generous margins between sections to create an "Editorial" breathing room.
* **Do** use `secondary` (#FFDF9E) sparingly for icons to draw the eye to "Special Offers."

### Don't
* **Don't** use pure white (#FFFFFF). Only use `on-surface` (#E5E2E1) or `primary-fixed` (#FFDBCF) to keep the "warm" aesthetic.
* **Don't** use standard 4px rounding. Use the `xl` (0.75rem) scale for cards and `full` for chips to keep the UI modern and approachable.
* **Don't** use "flat" black. Always use `surface` (#131313) to allow for depth layering.

### Accessibility Note
Maintain a high contrast ratio (minimum 4.5:1) for all `body-md` text. When using `primary` orange on `surface` backgrounds, ensure the font weight is at least Semi-Bold to maintain legibility.
