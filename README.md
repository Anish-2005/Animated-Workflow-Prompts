# THE DEFINITIVE MASTER PROMPTS: VANILLA HTML/CSS/JS HIGH-PERFORMANCE PORTFOLIO

These 5 exhaustive, highly detailed prompts are designed to be fed sequentially to an advanced AI coding agent. They are engineered to build a top 1%, minimal, and exceptionally smooth portfolio using **pure Vanilla HTML, CSS, and JavaScript**. This architecture prioritizes flawless 60fps performance on all devices by avoiding heavy JavaScript frameworks (like Next.js or React) and bloated animation libraries.

Each prompt is provided in a copyable block below.

---

## PROMPT 1: Foundational Architecture & Fluid Scroll Foundation

```text
Initialize a vanilla web project using strict HTML5, CSS3, and ES6 JavaScript (no React, no Next.js, no heavy frameworks). You can use a basic Vite setup or just raw `index.html`, `style.css`, and `main.js` files. We require a lightweight architecture capable of running smooth DOM animations effortlessly at a locked 60fps on both mobile and desktop.

Dependencies: Include `lenis` for smooth scrolling (via npm or CDN).

1. Global Scroll Foundation (Lenis):
- Initialize Lenis in your `main.js` for smooth scrolling. Use standard, lightweight settings: `lerp: 0.1` and `smoothWheel: true`. Set up the `requestAnimationFrame` loop strictly for Lenis.
- Use native document flow. Do not use artificial heights, absolute positioning traps, or fixed layout hacks.

2. Minimalist Design System & Fluid Typography:
- In `style.css`, implement CSS `clamp()` functions for heading typography to ensure seamless responsive scaling without media query breakpoints (e.g., `font-size: clamp(2rem, 5vw + 1rem, 5rem)`).
- Enforce an ultra-clean, high-contrast palette. Set CSS variables for `--port-bg: #FAFAFA`, `--port-text: #171717`, and `--port-accent: #525252`. Add a dark mode counterpart (`@media (prefers-color-scheme: dark)`).

3. Semantic Layout:
- Build a standard, accessible HTML shell in `index.html`. Ensure semantic tags (`<header>`, `<main>`, `<section>`, `<footer>`) are correctly utilized.
```

---

## PROMPT 2: The Visual Core — Performant Gradients & CSS Art

```text
Construct the visual background for the portfolio using pure CSS. Avoid Canvas elements or heavy JavaScript loops.

1. Subtle CSS Ambient Background:
- Create a lightweight background in your CSS using a performant `radial-gradient` or a subtle animated mesh gradient applied to a fixed pseudo-element (e.g., `body::before`).
- Animate the `background-position` slowly using CSS `@keyframes`, completely avoiding JavaScript for the animation tick.
- Keep the opacity extremely low (e.g., 5-10%) so it acts as a textural element.

2. SVG Grain Overlay:
- Implement a static SVG noise/grain overlay. Create a `.grain-overlay` div, set its `background-image` to a base64 inline SVG noise pattern. Set `opacity: 0.03`, `pointer-events: none;`, `position: fixed;`, `inset: 0;`, and `z-index: 50;`.
- Do not animate the noise with JS. Use a 2-step CSS `transform: translate()` keyframe to jitter the background slightly, generating a film-grain effect without taxing the GPU.

3. Clean Hero Section:
- Design a high-impact, minimalist hero section in HTML. Use whitespace and typography as the primary visual drivers. Focus on perfect CSS Flexbox or Grid alignment.
```

---

## PROMPT 3: Spatial Narrative & Vanilla Intersection Observer

```text
Develop the scroll-reveal animations using native browser APIs. Do not use GSAP or Framer Motion. The goal is a spatial narrative that feels alive without creating scroll lag.

1. Viewport-Based Reveals (`IntersectionObserver`):
- In `main.js`, create a single `IntersectionObserver` instance. Observe elements with a `.reveal` class.
- When an element enters the viewport (`isIntersecting`), add an `.is-visible` class and unobserve it.

2. CSS Transition Choreography:
- In `style.css`, define the base state for `.reveal`: `opacity: 0; transform: translateY(30px); transition: opacity 0.8s cubic-bezier(0.16, 1, 0.3, 1), transform 0.8s cubic-bezier(0.16, 1, 0.3, 1);`.
- Define the visible state: `.reveal.is-visible { opacity: 1; transform: translateY(0); }`.
- For staggered typography or lists, use CSS custom properties inline in the HTML (e.g., `style="--delay: 1"`) and apply `transition-delay: calc(var(--delay) * 100ms);` in the CSS.

3. Glassmorphism Optimization:
- If a floating header is needed, use highly optimized CSS: `backdrop-filter: blur(8px); background-color: rgba(255, 255, 255, 0.8);`. Avoid `saturate()` filters entirely.
```

---

## PROMPT 4: Native UX Micro-Interactions

```text
Focus on native, lightweight micro-interactions using vanilla JavaScript and CSS.

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
```

---

## PROMPT 5: Typography, Branding & Vanilla Performance Audit

```text
Finalize the minimal aesthetic with precise typography, crisp branding, and a flawless performance score.

1. Optimized Typographic Stack:
- Load variable Google Fonts efficiently via `<link rel="preconnect">` in the HTML `<head>`.
- Primary Headings: 'Inter' or 'Geist', tracked tight (`letter-spacing: -0.02em`) with a heavy font-weight.
- Body Copy: The same font, regular weight, high legibility (`line-height: 1.7`).

2. Clean SVG Branding:
- Create a minimal inline `<svg>` for the logo in the header. Use basic geometric shapes.
- Use a `.ico` or `.svg` file for the standard favicon.

3. Ruthless Performance Rules:
- Guarantee absolutely zero lag during fast scrolling.
- Avoid layout thrashing in JavaScript (never read from the DOM immediately after writing to it in the same frame).
- Only apply `will-change: transform` or `will-change: opacity` in CSS to elements that have persistent animations, and avoid applying it to too many elements.
- Keep the HTML DOM tree extremely shallow. Avoid unnecessary wrapper `<div>`s to ensure fast rendering.
```
