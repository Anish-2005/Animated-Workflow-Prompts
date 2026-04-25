# THE DEFINITIVE MASTER PROMPTS: ULTRA-ELITE MINIMALIST HIGH-PERFORMANCE PORTFOLIO

These 5 exhaustive, highly detailed prompts are designed to be fed sequentially to an advanced AI coding agent (e.g., Claude 3.5 Sonnet or GPT-4o). They are engineered to build a top 1%, minimal, and exceptionally smooth portfolio. This architecture prioritizes flawless 60fps performance on all devices (mobile and desktop) by avoiding heavy 3D rendering, laggy post-processing, and excessive DOM manipulation.

Each prompt is provided in a copyable block below.

---

## PROMPT 1: Foundational Architecture & Fluid Scroll Foundation

```text
Initialize an enterprise-grade Next.js 16 App Router project utilizing TypeScript and Tailwind CSS v4. This is an elite-level, minimalist personal portfolio. We require an architecture capable of running smooth DOM animations effortlessly at a locked 60fps on both mobile and desktop.

Dependencies: Install `framer-motion`, `lenis`, `clsx`, and `tailwind-merge`.

1. Global Scroll Foundation (Lenis):
- Instantiate Lenis at the root layout for smooth scrolling. Use standard, lightweight settings: `lerp: 0.1` and `smoothWheel: true`. Avoid tying heavy state updates to the scroll event. 
- Use native document flow. Do not use artificial heights, absolute positioning traps, or fixed layout hacks.

2. Minimalist Design System & Fluid Typography:
- Implement CSS `clamp()` functions for heading typography to ensure seamless responsive scaling without media query breakpoints (e.g., `font-size: clamp(2rem, 5vw + 1rem, 5rem)`).
- Enforce an ultra-clean, high-contrast palette. Set CSS variables for `--port-bg: #FAFAFA` (soft white), `--port-text: #171717` (deep neutral), and a subtle accent like `--port-accent: #525252`. Add a dark mode counterpart (`#0A0A0A` bg, `#EDEDED` text).

3. Semantic Layout:
- Build a standard, accessible HTML shell. Ensure semantic tags (`<header>`, `<main>`, `<section>`, `<footer>`) are used.
```

---

## PROMPT 2: The Visual Core — Performant Gradients & CSS Art

```text
Construct the visual background for the portfolio. Do not use heavy WebGL, Three.js, or Canvas particle swarms, as these destroy mobile battery life and laptop performance.

1. Subtle CSS Ambient Background:
- Create a lightweight background component using a performant CSS `radial-gradient` or a subtle animated mesh gradient. 
- Animate the `background-position` slowly using CSS keyframes, completely avoiding JavaScript for the animation tick.
- Keep the opacity extremely low (e.g., 5-10%) so it acts as a textural element rather than a focal point.

2. SVG Grain Overlay (Optional):
- Implement a static SVG noise/grain overlay. Set its `opacity` to `0.03` and `pointer-events: none`.
- Do not animate the noise with JS. If animation is required, use a 2-step CSS `transform: translate()` keyframe to jitter the SVG position slightly, ensuring negligible GPU load.

3. Clean Hero Section:
- Design a high-impact, minimalist hero section using whitespace and typography as the primary visual drivers. Avoid full-screen visual blockers. Focus on perfect spacing and alignment.
```

---

## PROMPT 3: Spatial Narrative & Lightweight Scroll Reveal

```text
Develop the content layer using `framer-motion`. The goal is to create a spatial narrative that feels alive without hijacking the user's browser or creating scroll lag.

1. Viewport-Based Reveals (`whileInView`):
- Instead of complex GSAP timelines bound to scroll progress, use Framer Motion's `whileInView` prop with `viewport={{ once: true, margin: "-100px" }}`.
- Animate elements sliding up gently (`y: 20` to `y: 0`) and fading in (`opacity: 0` to `opacity: 1`). Use natural spring transitions (`type: "spring", stiffness: 100, damping: 20`).

2. Staggered Typography:
- For the primary hero text, split the phrase into words or lines (not individual letters, to save DOM nodes and computation).
- Use `framer-motion` variants with `staggerChildren: 0.1` to cascade the text smoothly into view upon page load.

3. Glassmorphism Optimization:
- Avoid heavy `backdrop-filter` where possible. If glassmorphism is needed for navigation or floating headers, use a highly optimized version: `backdrop-filter: blur(8px)` combined with a semi-transparent solid background (`rgba(255,255,255,0.8)`). Avoid `saturate()` or `contrast()` filters entirely.
```

---

## PROMPT 4: Native UX Micro-Interactions

```text
Focus on native, lightweight micro-interactions that enhance the feel of the portfolio without running continuous requestAnimationFrame loops.

1. Native Cursor Excellence:
- Retain the native OS cursor. Do not implement custom JS cursors, as they cause significant latency on mobile and low-end devices.
- Instead, rely on rich CSS `:hover` states. Add subtle `transform: scale(1.02)` and `color` transitions to interactive elements. Use `cursor-pointer`.

2. Performant Magnetic CTAs (Optional/Light):
- If magnetic buttons are desired, restrict them to a few primary Calls to Action.
- Use a lightweight React `onMouseMove` handler on the button itself (not a global listener). Calculate the offset and apply a gentle `x` and `y` transform using Framer Motion's `useMotionValue` and `useSpring`. Reset to 0 on `onMouseLeave`. Do not offset inner text separately to avoid overdraw.

3. CSS-Driven Hover Cards:
- For project showcases, build interactive cards using pure CSS.
- On hover, reveal project details using `opacity` and a slight `transform: translateY(-5px)`. Use `transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1)`.
```

---

## PROMPT 5: Typography, Branding & Performance Audit

```text
Finalize the minimal aesthetic with precise typography, crisp branding, and a flawless performance score.

1. Optimized Typographic Stack (`next/font/google`):
- Use `next/font/google` to load variable fonts efficiently. 
- Primary Headings: 'Inter' or 'Geist', tracked tight (`letter-spacing: -0.02em`) with a heavy weight.
- Body Copy: The same font, regular weight, high legibility (`line-height: 1.7`).
- Monospace Accents: 'JetBrains Mono' for small technical details or labels, styled with uppercase and wide tracking.

2. Clean SVG Branding:
- Create a minimal SVG component for the logo/favicon. 
- Use basic geometric shapes (e.g., a simple grid, a circle intersecting a square, or minimal initials). Ensure it renders perfectly at 16x16px and scales beautifully without heavy gradients or drop shadows.

3. Ruthless Performance Rules:
- Guarantee absolutely zero lag during fast scrolling.
- Only apply `will-change: transform` or `will-change: opacity` to elements that are actively animating, and remove it immediately after the animation completes. Do not apply it globally.
- Audit the DOM tree depth. Keep it shallow. Avoid unnecessary wrapper `<div>`s to ensure fast rendering and rapid style recalculation by the browser.
```
