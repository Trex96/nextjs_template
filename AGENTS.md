You are a senior software engineer and technical documentation expert. 
I am giving you an HTML file (which may contain embedded CSS and JavaScript 
including animations, interactions, and UI logic).

Your task is to analyze the ENTIRE codebase thoroughly and write a complete, 
professional README.md documentation for it.

The README must cover the following sections:

---

## 📌 Project Overview
- What this project is and what it does
- The purpose and target audience
- A high-level summary of the UI/UX experience

---

## 🗂️ File & Code Structure
- Break down every major section of the HTML (head, body sections, key elements)
- List and explain all major CSS classes, IDs, and their roles
- List and explain all JavaScript functions, variables, and event listeners

---

## 🎨 Animation & Interaction Logic
- Explain EVERY animation in detail:
  - What it animates (element, property)
  - When it triggers (on load, on scroll, on click, on hover, etc.)
  - How it works (CSS keyframes, JS-driven, GSAP, ScrollTrigger, etc.)
  - The timing, easing, delay, and duration
- Explain all interaction flows (hover effects, click handlers, transitions)
- Describe the overall animation architecture and sequencing

---

## 🧩 Components & UI Sections
- Document each visible UI section/component
- What it contains, how it looks, how it behaves
- Any dynamic behavior or state changes

---

## ⚙️ Dependencies & Libraries
- List every external library, CDN, or framework used
- Version numbers if visible
- Purpose of each dependency

---

## 🚀 How to Run / Setup
- How to open or deploy this file
- Any requirements or prerequisites
- Browser compatibility notes if relevant

---

## 🔄 Data Flow & Logic
- Explain how data or state moves through the page (if applicable)
- Any DOM manipulation logic
- Dynamic content rendering

---

## 🛠️ Customization Guide
- How another developer can modify the animations
- How to change colors, timings, content
- Key variables or config values to tweak

---

## 📐 Code Architecture Decisions
- Why certain approaches were likely chosen
- Notable patterns used (e.g., GSAP timeline, IntersectionObserver, CSS custom properties)
- Any performance considerations visible in the code

---

RULES:
- Be extremely detailed and technical
- Write as if the reader has NEVER seen this codebase before
- Every animation must be documented — do not skip any
- Use code snippets where helpful to illustrate explanations
- Use clear headings, bullet points, and tables where appropriate
- The final README should be so complete that any developer 
  can fully understand, run, and modify this project without 
  asking a single question

Now analyze the HTML file I am providing and generate the full README.md.