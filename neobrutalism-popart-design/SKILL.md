---
name: neobrutalism-popart-design
description: Guidance for high-end, distinctive visual design combining strict Neobrutalism with vibrant Pop Art. Use this skill whenever the user requests premium components, landing pages, interactive menus, or layouts that require heavy borders, cartoon-style hard shadows, and high-saturation primary accent colors. Avoid basic or tutorial-grade styles.
---

# Neobrutalism & Pop Art Frontend Design Skill

This skill enforces high-end visual execution for web interfaces, stepping completely away from standard, templated SaaS designs into energetic, structural Pop Art.

## 1. Core Visual Tokens

### Borders & Contours
- ALWAYS use crisp, thick, heavy dark borders on all structural containers, cards, buttons, and input fields.
- Utility Class: Use `border-4 border-[#1A1A1A]` or `border-[5px] border-[#161616]`.

### Geometric Hard Shadows
- NEVER use soft blurs, ambient glows, or standard CSS ambient shadows. 
- All component elevation must be driven by flat, sharp, high-contrast, cartoon-style geometric hard shadows.
- Tailwind Arbitrary values: `shadow-[6px_6px_0px_0px_#1A1A1A]` or `shadow-[8px_8px_0px_0px_#000000]`.
- For smaller badges or tags: `shadow-[3px_3px_0px_0px_#1A1A1A]`.

### Pop Art Background Textures
- To elevate components beyond clean flats, use subtle retro pop patterns on the main wrapper or container backgrounds.
- Pattern Pattern: Integrate micro-grids, repeating dots, or radial patterns using subtle inline CSS:
```html
  background-image: radial-gradient(#1A1A1A 1px, transparent 1px);
  background-size: 16px 16px;

```

### Mechanical Interactive Pop Effects

* Hover and Active states must feel mechanical, snappy, and satisfying.
* When hovering over a card or button, it must "pop up" or push down against its shadow:
* Lift Effect: `hover:-translate-y-1 hover:-translate-x-1 hover:shadow-[10px_10px_0px_0px_#1A1A1A] transition-all`
* Push Effect (Click/Active): `active:translate-y-1 active:translate-x-1 active:shadow-[2px_2px_0px_0px_#1A1A1A]`



## 2. Color Architecture

* **Base/Background:** Clean, tinted cream, sand, or warm off-white base (`#FAF8F5` or `#F7F4EF`) to ground the canvas and let heavy elements punch through.
* **Primary Text:** Solid heavy charcoal or pure dark ink (`#1A1A1A`) for text, borders, and vector icons.
* **Vibrant Accent Pops:** Use highly saturated, explosive primary values sparingly for CTAs, badges, and floating status elements:
* Electric Yellow (`#FFE600`)
* Neon Cyan/Blue (`#00E5FF` or `#304FFE`)
* Hot Citrus Orange/Red (`#FF5722` or `#FF3D00`)



## 3. Typography Rules

* **Headlines:** Massive, ultra-bold, energetic sans-serif typography (`font-extrabold` or arbitrary `font-[900]` with `tracking-tight`). Ensure tight line-heights (`leading-none` or `leading-tight`).
* **Body:** Highly readable, clean modern sans-serif for comfort reading (`leading-relaxed text-[#2C2C2C]`).

