Love the concept — a **modern monochrome fashion webstore** with liquid-glass UI can absolutely score A+ if executed cleanly.

Below is a **clear, structured instruction document** you can give to your AI coding agent so it generates production-level code that matches your course rubric.

---

# 🧠 AI Coding Agent Instruction Document

## Project: Modern Fashion Webstore SPA

Course: CS3404 – GUI Programming Mini Project

---

## 1️⃣ Project Overview

Build a **modern, responsive Fashion Brand Webstore SPA** using:

* **Vue 3 (Composition API only)**
* **TypeScript (Strict Mode, zero `any`)**
* **Vite**
* **Tailwind CSS**
* **DummyJSON API** (`/products`, `/categories`, `/auth/login`)

The design must follow a **minimal monochrome theme (black, white, grey)** with:

* Smooth transitions
* Fluid layout
* Glassmorphism (liquid glass) UI components
* Micro-interactions
* Responsive behavior (mobile-first)

The app must feel like a **premium fashion brand website**, not a student demo.

---

# 2️⃣ Technical Stack (Mandatory)

### Core

* Vue 3 + Composition API
* TypeScript (`strict: true`)
* Vite
* Tailwind CSS

### Required Supporting Libraries

Install and configure:

```bash
npm install vue-router@4
npm install pinia
npm install axios
npm install @headlessui/vue
npm install @heroicons/vue
npm install @vueuse/core
```

Optional but recommended:

```bash
npm install tailwindcss-animate
npm install clsx
```

---

# 3️⃣ Architecture Rules (VERY IMPORTANT)

## ❌ Never:

* Use `any`
* Put all logic inside `App.vue`
* Hardcode API response shapes
* Mix Options API and Composition API
* Use inline styles

## ✅ Always:

* Define strict TypeScript interfaces for ALL API responses
* Use reusable components
* Separate logic into composables
* Keep components small and focused
* Use Pinia for global state
* Follow clean folder structure

---

# 4️⃣ Project Structure

```
src/
│
├── assets/
├── components/
│   ├── layout/
│   │   ├── NavBar.vue
│   │   ├── Footer.vue
│   │
│   ├── ui/
│   │   ├── GlassCard.vue
│   │   ├── GlassButton.vue
│   │   ├── Loader.vue
│   │
│   ├── product/
│   │   ├── ProductCard.vue
│   │   ├── ProductGrid.vue
│   │   ├── ProductFilter.vue
│
├── pages/
│   ├── HomeView.vue
│   ├── ProductDetailView.vue
│   ├── LoginView.vue
│
├── router/
│   └── index.ts
│
├── stores/
│   ├── cartStore.ts
│   ├── authStore.ts
│
├── composables/
│   ├── useProducts.ts
│   ├── useAuth.ts
│
├── types/
│   ├── product.ts
│   ├── auth.ts
│
├── App.vue
└── main.ts
```

---

# 5️⃣ API Integration (DummyJSON)

Use:

* `/products`
* `/products/category/:category`
* `/products/:id`
* `/auth/login`

Base URL:

```
https://dummyjson.com
```

Use **axios with typed responses**.

---

# 6️⃣ TypeScript Requirements

Create strict interfaces:

### Product Interface

```ts
export interface Product {
  id: number
  title: string
  description: string
  price: number
  discountPercentage: number
  rating: number
  stock: number
  brand: string
  category: string
  thumbnail: string
  images: string[]
}
```

### ProductsResponse

```ts
export interface ProductsResponse {
  products: Product[]
  total: number
  skip: number
  limit: number
}
```

### AuthResponse

```ts
export interface AuthResponse {
  id: number
  username: string
  email: string
  firstName: string
  lastName: string
  gender: string
  image: string
  token: string
}
```

Strict typing must propagate everywhere.

---

# 7️⃣ Required Features (For Distinction)

## 1️⃣ Product Listing

* Grid layout
* Responsive
* Smooth hover effects
* Image scale animation on hover
* Glass card UI

## 2️⃣ Search & Filtering

* Filter by category
* Real-time search by title
* No page reload

## 3️⃣ Product Detail Page

* Dynamic route: `/product/:id`
* Image gallery
* Add to Cart button
* Smooth page transition

## 4️⃣ Shopping Cart (Pinia)

* Add/remove items
* Persist in localStorage
* Reactive cart badge in navbar
* Cart drawer panel

## 5️⃣ Authentication Simulation

* Login page
* Call `/auth/login`
* Store JWT in localStorage
* Manage login/logout state
* Protect cart route (optional)

## 6️⃣ Dark Mode Toggle

* Use Tailwind `dark:` modifier
* Toggle stored in localStorage
* Smooth transition

---

# 8️⃣ UI Design System (Fashion Brand Style)

## Color System

Primary:

* Black: `#000000`
* White: `#FFFFFF`
* Neutral grays: Tailwind `neutral-100` to `neutral-900`

No bright colors.

Accent:

* Subtle grey hover states only.

---

# 9️⃣ Glassmorphism (Liquid Glass Style)

Use:

```css
backdrop-blur-xl
bg-white/10
border border-white/20
shadow-xl
```

For dark mode:

```css
dark:bg-black/40
dark:border-white/10
```

All glass components must:

* Have rounded corners (`rounded-2xl`)
* Smooth hover transitions
* Soft shadows

---

# 🔟 Animation & Fluidity

Use:

* `transition-all duration-300 ease-in-out`
* Scale on hover
* Fade transitions for route changes
* Smooth scrolling
* Loading skeletons

No janky animations.

Use `@vueuse/core` for:

* Scroll detection
* Dark mode
* Local storage sync

---

# 11️⃣ Responsiveness Rules

Mobile-first.

Use:

* `grid-cols-1`
* `sm:grid-cols-2`
* `lg:grid-cols-4`

Navbar:

* Hamburger menu on mobile
* Horizontal on desktop

Cart:

* Slide-in drawer on desktop
* Full-screen modal on mobile

---

# 12️⃣ Clean Component Rules

Each component must:

* Accept strictly typed props
* Emit typed events
* Have zero business logic if UI-only
* Follow single responsibility principle

Example:

* `ProductCard.vue` → UI only
* `useProducts.ts` → data logic

---

# 13️⃣ Performance Optimization

* Lazy-load routes
* Use `defineAsyncComponent` if needed
* Avoid unnecessary reactivity
* Use `computed` over `watch` when possible
* Key lists properly

---

# 14️⃣ Git Workflow Requirements

Use atomic commits:

Examples:

```
feat: setup project with vue + tailwind
feat: add typed product service
feat: implement product grid
feat: add dynamic product detail route
feat: implement pinia cart store
feat: add dark mode toggle
style: refine glassmorphism effects
refactor: extract product logic into composable
```

No single massive commit.

---

# 15️⃣ Code Quality Standards

The AI must:

* Never generate unused variables
* Never leave console.logs
* Never use `any`
* Use clean indentation
* Use meaningful naming
* Separate logic cleanly

---

# 16️⃣ Final Quality Goal

The final app should feel like:

* A modern fashion brand site
* Premium minimalist aesthetic
* Smooth and elegant
* Professional UI polish
* Production-ready architecture

Not like:

* A tutorial project
* A generic Bootstrap store
* A student assignment

---

If you'd like, I can next generate:

* 🎨 A **complete design direction guide (fonts, spacing, layout rules)**
* 🏗 A **step-by-step development roadmap**
* 🧩 Or the **initial project setup commands + config files**
* 🔥 Or a **ready-to-paste AI prompt log for your prompts.txt**

Tell me which one you want first.
