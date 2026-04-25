# THE DEFINITIVE MASTER PROMPTS: ULTRA-ELITE 3D CINEMATIC PORTFOLIO

These 5 exhaustive, highly detailed prompts are designed to be fed sequentially to an advanced AI coding agent (e.g., Claude 3.5 Sonnet or GPT-4o). They are engineered to bypass generic, boilerplate web development and force the output of a top 1%, Awwwards-winning, mathematically precise WebGL portfolio.

Each prompt is provided in a copyable block below.

---

## PROMPT 1: Foundational Architecture, Physics-Based Scroll Engine & State Synchronization

```text
Initialize an enterprise-grade Next.js 16 App Router project utilizing TypeScript, Tailwind CSS v4, and the React Compiler. This is an elite-level, cinematic personal portfolio. We require an architecture capable of running a heavy WebGL scene alongside complex DOM animations at a locked 60/120fps.

Dependencies: Install `three`, `@react-three/fiber`, `@react-three/drei`, `@react-three/postprocessing`, `gsap`, `lenis`, `framer-motion`, and `simplex-noise`.

1. Global Scroll Physics Engine (Lenis):
- Instantiate Lenis at the root layout. You must not use default settings. Apply a custom easing function: `ease: (t) => Math.min(1, 1.001 - Math.pow(2, -10 * t))` and set `lerp: 0.08` for heavy, buttery friction.
- CRITICAL: Create a high-performance proxy state (using `valtio` or a vanilla JS closure/singleton) to sync Lenis's `progress` (0 to 1) and `velocity` metrics. This proxy must bypass React's standard state (`useState`) entirely. GSAP's `ScrollTrigger` and React Three Fiber's `useFrame` will poll this proxy 120 times a second; using React state here will destroy performance via re-renders.

2. Fluid Typography & Design System:
- Implement CSS `clamp()` functions for absolutely all typographic elements to ensure sub-pixel fluid scaling (e.g., `font-size: clamp(2rem, 5vw + 1rem, 8rem)`). Avoid static Tailwind text utilities (like `text-4xl`) for primary headings.
- Enforce an elite 'Deep Space' palette. Set CSS variables for `--port-bg: #020203` (absolute dark), `--port-text: #E2E2E5` (off-white, reducing eye strain), and an intense chromatic accent like `--port-accent: #8B5CF6` (Neon Amethyst) or `#14B8A6` (Cyber Teal).

3. Cinematic Viewport Shell Setup:
- Build a `CinematicShell` layout component. The `<main>` tag must not scroll normally. Give it a massive artificial height, e.g., `height: 1500vh`. 
- Wrap the actual visual content in a `position: fixed`, `inset: 0`, and `overflow: hidden` container. This effectively traps the user's viewport in a fixed cinematic lens, mapping the 1500vh scroll distance entirely to the 3D camera timeline and GSAP overlays.
```

---

## PROMPT 2: The Neural Core — Custom GLSL Shaders & React Three Fiber

```text
Construct the `Fluid3DScene` component using React Three Fiber. This acts as the visual masterpiece of the portfolio, rendered behind all HTML.

1. The Monolith (Advanced Physical Transmission):
- Create a central geometric monolith (a mathematically deformed Icosahedron or complex Torus Knot). 
- Apply an ultra-advanced `MeshPhysicalMaterial`. The monolith must look like a solid piece of flint glass refracting the universe behind it. Use parameters: `transmission: 1.2`, `ior: 1.6`, `thickness: 2.5`, `roughness: 0.15`, `chromaticAberration: 0.08`, `dispersion: 2.0`, and `clearcoat: 1.0`.

2. GPGPU / FBO Particle Swarm:
- Do not use standard Three.js particle systems. Implement a Frame Buffer Object (FBO) simulation utilizing custom GLSL shaders to drive 10,000 micro-particles.
- Vertex Shader: Use `simplex-noise` to calculate 3D curl noise vectors. The particles must behave like fluid intelligence, constantly swirling and reacting to the monolith's gravitational center.
- Fragment Shader: Make the particles glow with the `--port-accent` color, fading at the edges. Use `@react-three/drei`'s `<PointMaterial>` or custom `RawShaderMaterial` for performant rendering.

3. Scroll-Velocity Camera Rig:
- Build a `CameraRig` component. Inside `useFrame`, read the `globalScrollProxy` (both `progress` and `velocity`).
- Interpolate the camera's `z` position and `fov` using `MathUtils.damp`. 
- Velocity Warp: When the `velocity` spikes (fast scroll), dynamically pull the FOV backwards and stretch the post-processing bloom to create a 'warp-speed' effect. When velocity hits 0, ease the FOV back to its resting state. Tie the user's mouse coordinates to a subtle, delayed parallax pan to keep the scene breathing.

4. Post-Processing & Optimization:
- Wrap the scene in an `EffectComposer`. Apply a high-pass `Bloom` (luminance threshold 0.6, intensity 2.5), `DepthOfField` (focus distance strictly mapped to the monolith's surface to blur background particles), and a heavy cinematic `Vignette`.
- CRITICAL PERF: Wrap the entire `<Canvas>` in `<Bvh>` (Bounding Volume Hierarchy). Disable `antialias` on the WebGL renderer since we are using heavy post-processing, and ensure `dpr={[1, 2]}` is capped to prevent mobile GPU throttling.
```

---

## PROMPT 3: Spatial Narrative Overlay & Z-Axis Staggering via GSAP

```text
Develop the `NarrativeOverlay` component. This is the HTML layer that tells the story. It must sit strictly above the 3D canvas (`z-10`), using `pointer-events-none` on the container so users can still interact with the 3D scene.

1. Master GSAP ScrollTrigger Architecture:
- Implement a single GSAP Master Timeline with `scrub: 1.2` mapped to the `1500vh` container. Use `gsap.matchMedia()` to handle breakpoints (desktop vs. mobile scaling logic).

2. The Void Entrance (Hero Sequence):
- Utilize `framer-motion` for the initial component mount. The hero typography (e.g., 'Creative Engineer') must materialize from absolute darkness. Animate `filter` from `blur(40px)` to `0px`, and `scale` from `1.5` to `1.0`. Use a heavy custom cubic-bezier curve `[0.16, 1, 0.3, 1]` spanning 3 full seconds.

3. 3D Typographic Flight (The Manifesto):
- Render a manifesto sequence (e.g., 'I don't write code. I engineer realities.'). Wrap each word in a span. 
- As the user scrolls, use GSAP to animate each individual word flying straight past the camera. Animate `translateZ` (from `-500px` deep in the background to `1000px` flying past the user's face). Combine this with `opacity` arcs (0 -> 1 -> 0) and slight `rotationX`. Apply `opacity-0` in Tailwind to all words initially to prevent any Flash of Unstyled Content (FOUC).

4. Glassmorphic HUD & Synced Spatial Carousel:
- Tech Stack HUD: Reveal floating technical panels demonstrating the tech stack. Use intense glassmorphism: `backdrop-filter: blur(24px) saturate(150%)`, `border: 1px solid rgba(255,255,255,0.05)`, and a subtle internal box-shadow. Map their `y` and `rotateY` transforms to the GSAP scroll scrub so they tilt dynamically in 3D space.
- Horizontal Projects Pan: At exactly 75% scroll progress, hijack the vertical scroll completely. Trigger a horizontal GSAP pan of massive case-study cards. Set `.pointer-events-auto` on these cards so they are clickable. Crucially, sync this horizontal HTML pan precisely with a horizontal camera pan in the WebGL scene, unifying the two layers.
```

---

## PROMPT 4: Physics-Based Micro-Interactions & Liquid UI

```text
An elite portfolio is defined entirely by its micro-interactions. You must implement the following physics-driven UX components to bridge the gap between static web and interactive application:

1. The Fluid Velocity Cursor:
- Suppress the native OS cursor (`cursor-none` on the body). Build a custom `Framer Motion` cursor using spring physics (`stiffness: 200, damping: 20`). 
- It must feature a 4px solid central dot and a massive 400px radial glow layer set to `mix-blend-screen`. 
- Velocity Distortion: Read the mouse velocity vector. When moving rapidly, the radial glow must dynamically stretch (`scaleX`) and skew along the exact angle of movement, returning to a perfect circle when resting.

2. Sub-Pixel Magnetic Parallax Buttons:
- Create an advanced `MagneticButton` wrapper. When the mouse approaches, calculate the bounding client rect and the exact distance to the button's center.
- Use GSAP to pull the button container towards the mouse (clamped to a max of 20px). 
- The Magic Touch: Pull the *text label inside* the button even further (clamped to 40px). This offset creates a stunning 3D parallax depth effect inside a 2D HTML button. Apply `scale: 0.95` smoothly on the `mousedown` event.

3. Velocity-Driven Scroll Momentum Indicator:
- Discard generic vertical progress bars. Create a fixed geometric HUD element (e.g., a technical wireframe dial or radar) in the bottom right corner. 
- Use an SVG `<circle>`. Map its `stroke-dashoffset` precisely to the Lenis `progress` (0 to 1). 
- Velocity Rotation: Rotate the entire SVG housing based on the immediate Lenis `velocity` metric. The faster the user scrolls, the faster the targeting dial spins, creating an immediate tactile connection between the user's mouse wheel and the UI.
```

---

## PROMPT 5: Brutalist Typography, Generative Branding & Master Polish

```text
Finalize the technical aesthetic. Focus on typographic perfection, generative SVG generation, and a ruthless performance audit.

1. Elite Typographic Stack (next/font/google):
- Import strictly variable fonts. Do not rely on system fallbacks.
- Display Layer: Use Syncopate or Oswald for massive, brutalist headers. Force uppercase, tight tracking (`letter-spacing: -0.05em`), and huge optical sizes.
- Body Layer: Use Inter or Geist. Optimize for extreme legibility. Keep paragraph widths sparse and enforce a precise line-height of `1.6`.
- Technical/HUD Layer: Use JetBrains Mono or Space Mono (For all technical data, scroll metrics, and micro-labels. Force uppercase with wide tracking `letter-spacing: 0.2em`).

2. Mathematical Generative Favicon (Next.js ImageResponse):
- Do not use a static PNG or ICO file. Utilize Next.js `app/icon.tsx` (`ImageResponse`) to generate a dynamic, mathematically perfect 2D vector logo on the fly.
- Construct a sharp, highly abstract geometric monogram representing the developer's initials (e.g., interlocking sharp triangles, or a monolithic architectural 'K').
- Use raw SVG `<path>` data. Apply an intensely glowing linear-gradient `stroke` (thickness `12px`) matching the `--port-accent` color, set against a deep `#020203` background. Add tiny geometric glowing circles at the apex vertices to sell the technical aesthetic.

3. Performance & Render Audit:
- Guarantee 60fps on mobile and 120fps on capable desktop monitors.
- Apply `will-change: transform, opacity` via CSS to all elements targeted by GSAP to force hardware acceleration.
- Ensure strict React Three Fiber memory management: use `useMemo` for all complex geometries, shader materials, and math vectors to prevent garbage collection stuttering during scroll.
- Verify the exact Z-index stack: 3D Canvas (`z-0`) -> Grain/Noise Overlay (`z-10`) -> Narrative Overlay (`z-20`) -> Interactive Project Carousel (`z-30`) -> Custom Cursor (`z-50`).
```
