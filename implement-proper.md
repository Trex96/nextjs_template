NEXTJS : proper



You are a senior full-stack developer with deep expertise in Next.js, 
React, TypeScript, Tailwind CSS, and modern frontend architecture.

I am giving you an HTML file that contains a complete UI — including 
structure, styling (CSS), and behavior (JavaScript/animations).

Your task is to convert and rebuild this ENTIRE HTML file into a 
production-grade Next.js application — professionally, cleanly, 
and completely.

---

## 🧠 CORE DIRECTIVE

Do NOT just copy-paste HTML into a React component.
Rebuild it the RIGHT way — the way a senior engineer at a top 
tech company would architect it from scratch.

---

## 📁 PROJECT SETUP

- Use Next.js 14+ with App Router
- Use TypeScript for all files (.tsx / .ts)
- Use Tailwind CSS for all styling
- Use proper folder structure:

  src/
  ├── app/
  │   ├── layout.tsx
  │   ├── page.tsx
  │   └── globals.css
  ├── components/
  │   ├── ui/           → reusable primitives
  │   └── sections/     → page sections
  ├── hooks/            → custom React hooks
  ├── lib/              → utilities & helpers
  ├── constants/        → config, static data
  └── types/            → TypeScript interfaces

---

## ⚙️ CONVERSION RULES

### HTML → React
- Convert all HTML sections into isolated, reusable React components
- Replace all class= with className=
- Replace inline styles with Tailwind classes wherever possible
- Convert all IDs used for JS targeting into React refs (useRef)
- Replace all querySelector / getElementById with useRef hooks
- Replace all addEventListener with React event handlers (onClick, 
  onMouseEnter, etc.)
- Convert all setTimeout / setInterval into useEffect with cleanup
- Move all hardcoded content (text, images, links) into constants/ 
  or a data file — never hardcoded inside JSX

### CSS → Tailwind + CSS Modules
- Convert ALL CSS to Tailwind utility classes
- If a style cannot be expressed in Tailwind, add it to a 
  CSS Module or globals.css using CSS custom properties
- Preserve ALL CSS variables as Tailwind theme extensions 
  in tailwind.config.ts
- Do NOT use arbitrary Tailwind values unless absolutely necessary

### JavaScript → React Hooks & TypeScript
- Rewrite ALL vanilla JS logic as typed React hooks or utilities
- Extract reusable logic into custom hooks in /hooks
- Type EVERYTHING — no `any`, no implicit types
- Handle all edge cases and null checks

---

## 🎬 ANIMATION MIGRATION

This is critical — preserve EVERY animation exactly as it appears 
in the original HTML.

- If the original uses GSAP:
  → Use GSAP inside useEffect with proper cleanup
  → Use ScrollTrigger with useLayoutEffect
  → Wrap in a custom useGSAP() hook
  → Install: gsap, @gsap/react

- If the original uses CSS animations/keyframes:
  → Migrate to Tailwind animate- classes or custom keyframes 
    in tailwind.config.ts

- If the original uses IntersectionObserver:
  → Create a useIntersectionObserver() custom hook

- If the original uses scroll events:
  → Create a useScrollPosition() custom hook

- Ensure animations:
  → Do NOT run on server (SSR-safe with dynamic import or 
    typeof window check)
  → Clean up properly on component unmount
  → Match original timing, easing, delay, and trigger behavior 
    EXACTLY

---

## 🖼️ ASSETS & MEDIA

- Move all image paths to /public folder
- Use Next.js <Image /> component for all images with:
  → Proper width and height
  → alt text
  → priority flag for above-the-fold images
- Use next/font for any Google Fonts used
- Replace all <a href> external links with Next.js <Link /> 
  where appropriate

---

## 📐 COMPONENT ARCHITECTURE RULES

- Each section of the page = one component in /components/sections/
- Each repeated UI element = one reusable component in /components/ui/
- Props must be fully typed with TypeScript interfaces in /types/
- Use default exports for page components, named exports for 
  UI primitives
- No component should be longer than 150 lines — split if needed
- No business logic inside JSX — extract into hooks or utils

---

## 🔧 CONFIGURATION FILES

Generate ALL of the following:
- tsconfig.json (strict mode enabled)
- tailwind.config.ts (with custom theme tokens from original CSS)
- next.config.ts (image domains, any required settings)
- package.json (all required dependencies with correct versions)
- .eslintrc.json (airbnb or next/core-web-vitals ruleset)
- postcss.config.js

---

## ✅ QUALITY CHECKLIST

Before finalizing, ensure:
- [ ] Zero TypeScript errors
- [ ] Zero ESLint warnings
- [ ] All animations work identically to the original
- [ ] Fully responsive (mobile → tablet → desktop)
- [ ] No hydration errors (SSR-safe)
- [ ] All images use <Image /> with required props
- [ ] No hardcoded colors — all from Tailwind theme
- [ ] Proper loading states if any async logic exists
- [ ] Semantic HTML throughout (section, article, nav, main, etc.)
- [ ] Accessible markup (aria-labels, roles, keyboard navigation)

---

## 📦 DELIVERABLES

Provide the following in order:

1. Complete folder structure (tree view)
2. package.json with all dependencies
3. tailwind.config.ts with all custom tokens
4. tsconfig.json
5. next.config.ts
6. src/app/layout.tsx
7. src/app/globals.css
8. src/app/page.tsx
9. Every component file (sections + ui)
10. Every custom hook file
11. Every constants / types file
12. Brief explanation of any key architectural decision made

---

## 🚨 STRICT RULES

- Do NOT skip any section of the original HTML
- Do NOT simplify or remove any animation
- Do NOT leave any placeholder like "// add logic here"
- Do NOT use class components — hooks only
- Do NOT use any as a TypeScript type
- Every file must be complete and immediately runnable
- The final result must be a pixel-perfect, animation-perfect 
  replica of the original — built to production standard

Now analyze the HTML file I am providing and convert it 
into the complete Next.js codebase.