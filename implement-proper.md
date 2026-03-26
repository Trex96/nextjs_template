NEXTJS : proper


You are a senior full-stack developer with deep expertise in Next.js, 
React, TypeScript, Tailwind CSS, and modern frontend architecture.

I am giving you:
1. An HTML file that contains a complete UI — including structure, 
   styling (CSS), and behavior (JavaScript/animations)
2. A folder of assets — including images, icons, fonts, videos, 
   SVGs, and any other media files used in the project

Your task is to convert and rebuild this ENTIRE HTML file into a 
production-grade Next.js application — professionally, cleanly, 
and completely — using the exact assets I have provided.

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

  public/
  ├── images/           → all raster images (.jpg, .png, .webp)
  ├── icons/            → all icon files (.svg, .ico, .png)
  ├── fonts/            → any local font files
  ├── videos/           → any video files (.mp4, .webm)
  └── assets/           → any other static assets

---

## 🗂️ ASSETS HANDLING (CRITICAL)

I have provided you with the original assets folder alongside 
the HTML file. Follow these rules strictly:

### Images
- Map EVERY image referenced in the HTML to its exact file 
  from the provided assets folder
- Place all images in /public/images/ maintaining original 
  subfolder structure if any
- Use Next.js <Image /> component for ALL images with:
  → Correct src path pointing to /public folder
  → Exact or estimated width and height
  → Descriptive alt text based on context
  → priority={true} for any above-the-fold / hero images
  → loading="lazy" for below-the-fold images

### SVGs
- Inline critical SVGs (icons, logos) directly as React 
  components in /components/ui/icons/
- Place decorative/background SVGs in /public/icons/
- Never use <img> for SVGs that need color control — 
  convert them to React SVG components with fill="currentColor"

### Fonts
- If fonts are local files in assets → move to /public/fonts/ 
  and load via next/font/local in layout.tsx
- If fonts are Google Fonts → replace with next/font/google
- Never use a raw <link> tag for fonts in Next.js

### Videos
- Place all video files in /public/videos/
- Use HTML5 <video> tag with proper attributes:
  → autoPlay, muted, loop, playsInline for background videos
  → controls for user-facing videos
  → Add poster attribute using a frame image from assets

### Icons
- If the project uses icon libraries (Font Awesome, etc.) 
  replace with lucide-react or react-icons
- Match every icon visually to its original
- Install: npm install lucide-react

### Asset Path Mapping
- Audit EVERY src=, href=, url() reference in the original HTML
- Map each one to its corresponding file in the provided assets
- If an asset is missing, note it clearly as:
  // MISSING ASSET: original path was "assets/xyz.png" 
  // — replace with correct file

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

## 🖼️ NEXT.JS IMAGE COMPONENT RULES

Every image in the project must follow this pattern:

import Image from 'next/image'

<Image
  src="/images/filename.jpg"       ← exact path in /public
  alt="descriptive alt text"       ← always meaningful
  width={1200}                     ← actual or estimated px
  height={800}                     ← actual or estimated px
  priority={true}                  ← only for hero/above-fold
  className="..."                  ← Tailwind classes
/>

For background images that must be CSS-driven:
- Use Tailwind bg- utilities with custom values in config
- Or use a wrapper div with a Next.js <Image> set to fill + 
  object-cover with position="relative" on parent

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
- [ ] All assets correctly referenced and placed in /public
- [ ] No broken image paths or missing asset references
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

1. Complete folder structure (tree view) including all 
   assets mapped to /public
2. Asset mapping table:
   ORIGINAL PATH → NEW /public PATH → COMPONENT USED IN
3. package.json with all dependencies
4. tailwind.config.ts with all custom tokens
5. tsconfig.json
6. next.config.ts
7. src/app/layout.tsx
8. src/app/globals.css
9. src/app/page.tsx
10. Every component file (sections + ui)
11. Every custom hook file
12. Every constants / types file
13. Brief explanation of any key architectural decision made

---

## 🚨 STRICT RULES

- Do NOT skip any section of the original HTML
- Do NOT simplify or remove any animation
- Do NOT leave any placeholder like "// add logic here"
- Do NOT use class components — hooks only
- Do NOT use any as a TypeScript type
- Do NOT change or rename any provided asset files
- Do NOT use placeholder images — use the exact assets provided
- Every file must be complete and immediately runnable
- The final result must be a pixel-perfect, animation-perfect, 
  asset-perfect replica of the original — built to production standard

Now analyze the HTML file and all assets I am providing 
and convert everything into the complete Next.js codebase.
