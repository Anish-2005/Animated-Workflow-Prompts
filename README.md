# THE DEFINITIVE MASTER PROMPTS: ENGINEERING STUDENT VANILLA HTML/CSS/JS PORTFOLIO

These 5 exhaustive, highly detailed prompts are designed to be fed sequentially to an advanced AI coding agent. They are engineered to build a visually attractive, colorful, technically credible engineering-student portfolio using **pure Vanilla HTML, CSS, and JavaScript**. The result should feel ambitious, modern, and polished without becoming bloated or generic. The architecture prioritizes flawless 60fps performance on all devices by avoiding heavy JavaScript frameworks (like Next.js or React) and bloated animation libraries, while still enabling a section-aware pseudo-3D background that repositions itself smoothly as the user scrolls.

Each prompt is provided in a copyable block below.

Before using the prompts, replace the placeholders below with the user's preferred identity, color palette, and visual direction.

## USER INPUT PLACEHOLDERS

Use these exact placeholders inside the prompts and swap them before generation:

- `[STUDENT_NAME]`
- `[ENGINEERING_DISCIPLINE]` such as Mechanical Engineering, Computer Science, Electronics, Civil Engineering
- `[UNIVERSITY_NAME]`
- `[TAGLINE]`
- `[PORTFOLIO_VIBE]` such as futuristic lab, clean academic, colourful systems UI, bold tech showcase
- `[PRIMARY_COLOR]`
- `[SECONDARY_COLOR]`
- `[ACCENT_COLOR]`
- `[BACKGROUND_LIGHT]`
- `[BACKGROUND_DARK]`
- `[TEXT_LIGHT]`
- `[TEXT_DARK]`
- `[CARD_TINT]`
- `[HERO_MOOD]` such as precise, playful, bold, experimental, research-driven
- `[PROJECT_AREAS]` such as robotics, embedded systems, CAD, web development, AI, circuits
- `[CTA_LABEL_PRIMARY]`
- `[CTA_LABEL_SECONDARY]`

---

## PROMPT 1: Foundational Architecture & Fluid Scroll Foundation

```text
Initialize a vanilla web project using strict HTML5, CSS3, and ES6 JavaScript (no React, no Next.js, no heavy frameworks). You can use a basic Vite setup or just raw `index.html`, `style.css`, and `main.js` files. We require a lightweight architecture capable of running smooth DOM animations effortlessly at a locked 60fps on both mobile and desktop.

This portfolio is for `[STUDENT_NAME]`, a `[ENGINEERING_DISCIPLINE]` student from `[UNIVERSITY_NAME]`. The final site should feel like a high-end engineering portfolio: technically serious, visually attractive, colorful, and tailored to the vibe `[PORTFOLIO_VIBE]` with the mood `[HERO_MOOD]`.

Dependencies: Include `lenis` for smooth scrolling (via npm or CDN).

1. Global Scroll Foundation (Lenis):
- Initialize Lenis in your `main.js` for smooth scrolling. Use standard, lightweight settings: `lerp: 0.1` and `smoothWheel: true`. Set up the `requestAnimationFrame` loop strictly for Lenis.
- Use native document flow. Do not use artificial heights, absolute positioning traps, or fixed layout hacks.

2. Minimalist Design System & Fluid Typography:
- In `style.css`, implement CSS `clamp()` functions for heading typography to ensure seamless responsive scaling without media query breakpoints (e.g., `font-size: clamp(2rem, 5vw + 1rem, 5rem)`).
- Enforce an ultra-clean but colorful palette driven by user-provided placeholders. Set CSS variables such as `--port-primary: [PRIMARY_COLOR]`, `--port-secondary: [SECONDARY_COLOR]`, `--port-accent: [ACCENT_COLOR]`, `--port-bg: [BACKGROUND_LIGHT]`, and `--port-text: [TEXT_LIGHT]`. Add a dark mode counterpart using `[BACKGROUND_DARK]` and `[TEXT_DARK]`.
- Preserve strong contrast and technical clarity even when the palette becomes vibrant.

3. Semantic Layout:
- Build a standard, accessible HTML shell in `index.html`. Ensure semantic tags (`<header>`, `<main>`, `<section>`, `<footer>`) are correctly utilized.
- Structure the portfolio for an engineering student: hero, about, skills/stack, project showcase, experience or achievements, and contact.
```

---

## PROMPT 2: The Visual Core - Performant Gradients, CSS Art & Faux 3D Scene

```text
Construct the visual background for the portfolio using pure CSS and lightweight DOM elements. Avoid Canvas elements, WebGL, or heavy JavaScript loops.

The overall visual language should feel like `[PORTFOLIO_VIBE]`, using `[PRIMARY_COLOR]`, `[SECONDARY_COLOR]`, `[ACCENT_COLOR]`, and `[CARD_TINT]` tastefully. The result should be colorful and memorable, but still credible for an engineering student.

1. Subtle CSS Ambient Background:
- Create a lightweight background in your CSS using a performant `radial-gradient` or a subtle animated mesh gradient applied to a fixed pseudo-element (e.g., `body::before`).
- Animate the `background-position` slowly using CSS `@keyframes`, completely avoiding JavaScript for the animation tick.
- Keep the opacity extremely low (e.g., 5-10%) so it acts as a textural element.
- Use the supplied colors as inputs. For example, derive gradient stops from `[PRIMARY_COLOR]`, `[SECONDARY_COLOR]`, and `[ACCENT_COLOR]` rather than hardcoding grayscale values.

2. SVG Grain Overlay:
- Implement a static SVG noise/grain overlay. Create a `.grain-overlay` div, set its `background-image` to a base64 inline SVG noise pattern. Set `opacity: 0.03`, `pointer-events: none;`, `position: fixed;`, `inset: 0;`, and `z-index: 50;`.
- Do not animate the noise with JS. Use a 2-step CSS `transform: translate()` keyframe to jitter the background slightly, generating a film-grain effect without taxing the GPU.

3. Clean Hero Section:
- Design a high-impact hero section in HTML for `[STUDENT_NAME]`. Use whitespace, typography, and color as the primary visual drivers. Focus on perfect CSS Flexbox or Grid alignment.
- Include placeholders in the content such as the student's name, discipline, tagline `[TAGLINE]`, and one or two concise lines about `[PROJECT_AREAS]`.
- The hero should feel attractive and energetic, not flat monochrome.

4. CSS-Built 3D Background Scene:
- Create a single fixed `.scene` container in the HTML that sits behind the content but above the base page background. Inside it, build 2-4 abstract DOM elements (for example: an orb, a slab, a ring) using gradients, borders, transparency, blur, and `transform-style: preserve-3d`.
- Build these background objects entirely with CSS. Use perspective on a parent `.scene-stage`, then compose each object with transforms such as `translate3d()`, `rotateX()`, `rotateY()`, and `rotateZ()`.
- Keep the objects subtle and atmospheric. They must never overpower the typography or reduce readability.
- Color the 3D objects using the chosen palette placeholders so the faux-3D scene feels personalized to the user rather than generic black-and-white glass.
- Do not create one background object per section. Instead, create one persistent fixed scene that will later be repositioned per section through lightweight JavaScript.
```

---

## PROMPT 3: Spatial Narrative, Scroll-Reveal & Section-Aware 3D Motion

```text
Develop the scroll-reveal animations and section-aware 3D background behavior using native browser APIs. Do not use GSAP or Framer Motion. The goal is a spatial narrative that feels alive without creating scroll lag.

The narrative should read like an engineering student portfolio journey: introduction, technical strengths, selected projects, achievements, and contact.

1. Viewport-Based Reveals (`IntersectionObserver`):
- In `main.js`, create a single `IntersectionObserver` instance. Observe elements with a `.reveal` class.
- When an element enters the viewport (`isIntersecting`), add an `.is-visible` class and unobserve it.

2. CSS Transition Choreography:
- In `style.css`, define the base state for `.reveal`: `opacity: 0; transform: translateY(30px); transition: opacity 0.8s cubic-bezier(0.16, 1, 0.3, 1), transform 0.8s cubic-bezier(0.16, 1, 0.3, 1);`.
- Define the visible state: `.reveal.is-visible { opacity: 1; transform: translateY(0); }`.
- For staggered typography or lists, use CSS custom properties inline in the HTML (e.g., `style="--delay: 1"`) and apply `transition-delay: calc(var(--delay) * 100ms);` in the CSS.
- Use staggering for engineering-specific content like skill lists, project metrics, coursework, achievements, or lab highlights.

3. Glassmorphism Optimization:
- If a floating header is needed, use highly optimized CSS: `backdrop-filter: blur(8px); background-color: rgba(255, 255, 255, 0.8);`. Avoid `saturate()` filters entirely.

4. Section-Aware 3D Background Repositioning:
- Mark each major section with a semantic targeting hook such as `.scene-target` and a `data-scene` identifier (`hero`, `about`, `projects`, etc.).
- In `main.js`, define a small object of pre-authored scene states for each section. Each state should contain transform values for the persistent 3D background elements (for example `tx`, `ty`, `tz`, `rx`, `ry`, `rz`, `scale`).
- Measure the sections only on load and resize. Cache their top offsets. Do not query layout on every animation frame.
- On scroll, compute which section range the user is in and smoothly interpolate between the current section's scene state and the next section's scene state.
- Apply the interpolated values by writing CSS custom properties or inline styles to the fixed background elements only. The scene should appear to adjust itself to each section as the user scrolls, without adding lag.
- Make the scene feel intentionally composed per section. For example: more open and bold in the hero, more structured in the skills section, more dynamic in the projects section, and calmer near contact.
- If `prefers-reduced-motion` is enabled, freeze the scene into a stable default state and skip the interpolation logic.
```

---

## PROMPT 4: Native UX Micro-Interactions

```text
Focus on native, lightweight micro-interactions using vanilla JavaScript and CSS.

The micro-interactions should make the site feel premium and colorful without becoming playful in a childish way. The audience should read it as a serious engineering student with strong design taste.

1. Native Cursor Excellence:
- Retain the native OS cursor. Do not implement custom JS cursors.
- Rely on rich CSS `:hover` states. Add subtle `transform: scale(1.02)` and `color` transitions to interactive elements. Use `cursor: pointer;`.

2. Performant Magnetic CTAs (Vanilla JS):
- For a few primary CTA buttons, add a `.magnetic` class.
- In `main.js`, add a `mousemove` event listener to these specific buttons. Calculate the mouse position relative to the button's center.
- Update CSS custom variables on the button (`--x` and `--y`) directly via `element.style.setProperty`.
- In CSS, apply `transform: translate(var(--x, 0), var(--y, 0)); transition: transform 0.1s linear;`. On `mouseleave`, reset `--x` and `--y` to 0 and change the transition to a smooth spring-like curve `transition: transform 0.5s cubic-bezier(0.3, 2, 0.4, 1);`.

3. CSS-Driven Hover Cards:
- Build interactive project showcase cards using pure HTML/CSS.
- On hover, reveal details using `opacity` and a slight `transform: translateY(-5px)`. Use `transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1)`.
- The cards should showcase engineering work: project title, short summary, tools used, result/impact, and a technical tag or metric.
- Use `[CARD_TINT]`, `[PRIMARY_COLOR]`, or `[ACCENT_COLOR]` selectively for borders, glows, tags, or card highlights.

4. Scroll-Safe Interaction Boundaries:
- Ensure the magnetic CTA logic and the section-aware 3D background logic never fight each other. Keep CTA interactivity scoped to the buttons themselves, and keep the faux-3D scene writes isolated to the fixed background elements.
- Use `requestAnimationFrame` only for Lenis and any already-running scroll-sync work. Do not spawn extra perpetual loops for hover effects.
```

---

## PROMPT 5: Typography, Branding & Vanilla Performance Audit

```text
Finalize the minimal aesthetic with precise typography, crisp branding, and a flawless performance score.

The completed site should clearly read as the portfolio of `[STUDENT_NAME]`, a `[ENGINEERING_DISCIPLINE]` student, with a vibrant but disciplined identity shaped by `[PORTFOLIO_VIBE]`.

1. Optimized Typographic Stack:
- Load variable Google Fonts efficiently via `<link rel="preconnect">` in the HTML `<head>`.
- Primary Headings: 'Inter' or 'Geist', tracked tight (`letter-spacing: -0.02em`) with a heavy font-weight.
- Body Copy: The same font, regular weight, high legibility (`line-height: 1.7`).

2. Clean SVG Branding:
- Create a minimal inline `<svg>` for the logo in the header. Use basic geometric shapes.
- Use a `.ico` or `.svg` file for the standard favicon.
- Make the branding suitable for an engineering student portfolio. It can reference initials, circuit traces, geometric construction, grids, or lab-inspired forms.

3. Ruthless Performance Rules:
- Guarantee absolutely zero lag during fast scrolling.
- Avoid layout thrashing in JavaScript (never read from the DOM immediately after writing to it in the same frame).
- Only apply `will-change: transform` or `will-change: opacity` in CSS to elements that have persistent animations, and avoid applying it to too many elements.
- Keep the HTML DOM tree extremely shallow. Avoid unnecessary wrapper `<div>`s to ensure fast rendering.
- For the faux-3D background scene, prefer 2-4 persistent fixed DOM elements instead of many layered nodes. Cache section metrics, reuse one scene, and only update transforms.
- Ensure the section-aware scene remains visually aligned on both desktop and mobile. Recalculate cached section positions on resize or orientation change only.
- Avoid generic portfolio copy. Use concise, high-signal text blocks oriented around engineering projects, build quality, tools, results, and academic credibility.
- Preserve the user palette placeholders in the implementation logic so future users can restyle the entire portfolio by changing the color variables only.
```
