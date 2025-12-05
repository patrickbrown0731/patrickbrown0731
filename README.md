# Hi there 👋 I'm Patrick - GSAP, CSS Animation, Three.js Expert

<p align="center">
  <img src="https://camo.githubusercontent.com/cf34bff7a1524df8ccb4e2f0c70edda3702a88305f98b82bcf7903591cd6b706/68747470733a2f2f6d656469612e67697068792e636f6d2f6d656469612f54456e586b637348725034596564436868412f67697068792e676966" alt="animation-banner" width="720"/>
</p>

I build interactive, motion-first web experiences and 3D visuals. My focus is on animation systems, performant rendering, and polished UI motion using modern web tools and libraries.

## About Me
- 🔭 I’m currently working on: portfolio pieces and interactive demos that showcase advanced 2D & 3D animation techniques.
- 🌱 I’m learning: advanced WebGL optimizations, real-time rendering patterns, and shader workflows.
- 👯 I’m looking to collaborate on: immersive web apps, web-based visualizations, and experimental UI animation.
- 💬 Ask me about: React, Next.js, Three.js, React Three Fiber, GSAP, GLSL, animation architecture, and performance tuning.
- ⚡ Fun fact: I love converting motion design concepts into reusable animation systems and components.

## Core Skills
- Frameworks & libraries: React, Next.js, React Three Fiber
- 3D & graphics: Three.js, GLSL shaders, post-processing, model pipelines
- Animation: GSAP (timelines + integrations), Framer Motion, timeline-based orchestration
- Motion systems: reusable animation primitives, state-driven motion, sequencing
- Languages & tooling: JavaScript, TypeScript, Vite, Webpack
- Testing & infra: Jest, Playwright, GitHub Actions
- Backend & data: Node.js, Express, PostgreSQL (when projects require fullstack)

## Animation Spotlight
A concise showcase of the approach and patterns I bring to animation-heavy projects.

- Motion-first design: I treat motion as a primary UX layer — defined early in the design and implemented with reusable systems.
- Timeline-driven orchestration: I structure complex sequences with GSAP timelines, allowing deterministic, testable animation flows.
- 3D + UI synergy: I bridge UI and 3D scenes (React ↔ r3f) so transitions and interactions feel cohesive across layers.
- Progressive enhancement: Animations are optimized for performance and have fallbacks for lower-end devices and reduced-motion preferences.
- Prototyping speed: Rapid demos using codesandbox/live examples to validate motion concepts before production.

Example (GSAP + React pattern)
```jsx
// Example: GSAP timeline inside a React component
import { useEffect, useRef } from "react";
import gsap from "gsap";

function Hero() {
  const ref = useRef(null);

  useEffect(() => {
    const ctx = gsap.context(() => {
      const tl = gsap.timeline({ defaults: { ease: "power2.out" } });
      tl.from(".title", { y: 24, opacity: 0, duration: 0.6 })
        .from(".subtitle", { y: 16, opacity: 0, duration: 0.5 }, "-=0.3")
        .from(".card", { y: 12, opacity: 0, stagger: 0.08, duration: 0.45 }, "-=0.25");
    }, ref);

    return () => ctx.revert();
  }, []);

  return (
    <section ref={ref}>
      <h1 className="title">Interactive Motion</h1>
      <p className="subtitle">Built with GSAP + React</p>
      <div className="card">Demo card</div>
    </section>
  );
}
```

Three.js + r3f integration pattern
- Keep heavy updates off the React render path (useFrame, refs, and memoized geometries).
- Reduce draw calls: merge geometries, use instancing, and minimize material/shader switches.
- Post-process selectively: compose effects only when they add clear value and budget them per frame.

---
