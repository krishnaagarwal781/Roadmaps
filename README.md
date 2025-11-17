# 💡 Next.js Engineering Onboarding: The Path to Production
## Next.js 15/16 App Router Focus — **For Incoming Engineering Interns**

**Prepared by:** Krishna Agarwal  
**Date:** November 2025  
**Version:** 1.0

---

## I. Essential Foundations: The Non-Negotiables
This list serves as your mandatory pre-flight checklist. **Do not proceed to the Next.js roadmap until you are comfortable with these topics.**

### 1. JavaScript (ES6+)
A production-ready application demands modern, efficient JavaScript. Focus on **mastery**, not just familiarity.

- **Syntax & Scope:** `let`/`const`, arrow functions  
- **Async JavaScript:** Promises, `async/await`  
- **Array Methods:** `map`, `filter`, `reduce`  
- **Modules:** ES Modules (`import` / `export`)  
- **Data Access:** `fetch()` + proper error handling  

### 2. TypeScript Basics (Mandatory)
We use TypeScript everywhere — it prevents runtime bugs.

- Types, interfaces  
- Generics + utility types  
- Type narrowing  
- Correctly typing API responses  

### 3. React Fundamentals
Next.js relies on modern React.

- Functional components  
- Props + state  
- Hooks: `useState`, `useEffect`, `useRef`, `useCallback`  
- Context API  
- Understanding **React Server Components (RSC)**  
- The role of **Suspense**  

### 4. HTML & CSS
Modern layouts require modern CSS.

- Flexbox + Grid  
- Responsive design  
- TailwindCSS basics  
- CSS animations  

### 5. Git & GitHub Workflow
Clean collaboration is mandatory.

- Branching strategy  
- Pull Requests (PRs)  
- Handling merge conflicts  

### 6. Basic API Knowledge
Full-stack applications require backend understanding.

- REST API basics  
- JSON  
- Authentication (sessions, tokens)  

---

## II. The Next.js 15/16 App Router Roadmap

### 🔹 Step 1 — Next.js Fundamentals (App Router)

| Concept | Artifacts | Notes |
|--------|-----------|-------|
| Folder Structure | `app/`, `page.tsx`, `layout.tsx` | Core of App Router |
| UI Boundaries | `loading.tsx`, `error.tsx` | Improve user experience |
| Routing | Nested, Parallel, Intercepting | Needed for modals & complex flows |
| Layouts | Layouts vs Templates | Layout persists state, template resets |

### 🔹 Step 2 — Rendering Strategies

| Strategy | Description | Notes |
|----------|-------------|-------|
| **SSR** | Server-rendered on request | Default for RSC |
| **SSG** | Build-time static | Good for marketing pages |
| **ISR** | Static + Refresh interval | Use `revalidate` |
| **CSR** | Client render only | Avoid unless necessary |
| **PPR** | Partial Prerendering | Modern approach using Suspense |

**Core Decisions:**

- Prefer **server components**  
- Use `<Suspense>` for streaming UI  

### 🔹 Step 3 — Data Fetching
Fetch data on the **server** wherever possible.

1. **Native fetch()**
   - `cache: 'force-cache'`
   - `cache: 'no-store'`
   - `revalidate: 10`
   - `export const dynamic = "force-static"`

2. **Server Actions**
   - `"use server"`
   - Replace simple POST/PUT APIs
   - Useful for secure mutations

3. **API Routes (Route Handlers)**
   - `app/api/users/route.ts`
   - Used for webhooks + complex endpoints

### 🔹 Step 4 — Database Integration
- Recommended: **Prisma + PostgreSQL**
- Connection pooling required for Vercel
- Never expose secrets to client

### 🔹 Step 5 — Authentication (NextAuth v5 + Middleware)
- NextAuth v5 (Auth.js)
- Middleware to protect routes  
- Edge runtime for faster checks  
- Cookie vs localStorage security  

### 🔹 Step 6 — State Management

| State | Tool |
|-------|------|
| Local UI | `useState`, `useReducer` |
| Global UI | Zustand, Jotai |
| Server State | **React Query** |

### 🔹 Step 7 — Performance Optimization
- Use `next/image`
- Code splitting  
- Use ISR + PPR  
- Avoid unnecessary client components  

### 🔹 Step 8 — File Uploads
Two types:

1. Signed URL (S3, Cloudinary)  
2. Streaming upload support in Next.js  

### 🔹 Step 9 — Payments
- Stripe Checkout  
- Server-only payment logic  
- Webhooks through route handlers  

### 🔹 Step 10 — Testing
- Jest + RTL  
- Playwright  

### 🔹 Step 11 — Deployment
- Vercel build + logs  
- Revalidate-on-demand  
- Docker + NGINX  
- GitHub Actions (CI/CD)  

---

## III. Recommended External Resources  
**With specific topic-based videos**

---

### 🎥 App Router / Core Next.js
- **Next.js App Router Course – Thapa Technical**  
  https://youtu.be/KBSYutEDkgw?si=LISlfWDUy9lIBomE

- **Routing, Layouts, Nested Routes – Codevolution**  
  https://www.youtube.com/watch?v=ZVnjOPwW4ZA

- **Parallel & Intercepting Routes – Codevolution**  
  https://www.youtube.com/watch?v=pUNSHPyVryU

- **Loading & Error UI – Codevolution**  
  https://www.youtube.com/watch?v=PqZBQPjyYfE

---

### 🎥 Rendering Strategies
- **SSR / SSG / ISR Explained** – Codevolution  
  https://www.youtube.com/watch?v=Hsx3RMkf23E

- **Partial Pre-Rendering (PPR)** – Fireship  
  https://www.youtube.com/watch?v=v0t42xBIYIs

---

### 🎥 Data Fetching + Server Actions
- **Server Components Data Fetching – Antonio**  
  https://www.youtube.com/watch?v=HeJpZXcKpos&t=1480

- **Server Actions Explained – Antonio**  
  https://www.youtube.com/watch?v=eiV_lF7dV5A

- **API Route Handlers – Codevolution**  
  https://www.youtube.com/watch?v=5fEvJBKk5ng

---

### 🎥 Databases (Prisma)
- **Next.js + Prisma Full Tutorial – Antonio**  
  https://www.youtube.com/watch?v=WirZsLT2rsA

---

### 🎥 Authentication
- **NextAuth App Router – Antonio**  
  https://www.youtube.com/watch?v=PuOVqP_cjkE

- **NextAuth v5 Full Tutorial – Antonio**  
  https://www.youtube.com/watch?v=Jq3cwxw2njU

---

### 🎥 State Management
- **React Query Crash Course – Net Ninja**  
  https://www.youtube.com/watch?v=8K2ihr8bl5I

- **Zustand in 10 Minutes – Fireship**  
  https://www.youtube.com/watch?v=Gx4iBLKLVHk

---

### 🎥 Performance Optimization
- **next/image Optimization – Codevolution**  
  https://www.youtube.com/watch?v=3PoeU6nZqy0

- **React Server Components Explained – Fireship**  
  https://www.youtube.com/watch?v=TQQPAU21ZUw

---

### 🎥 File Uploads
- **Next.js File Uploads using Server Actions – Antonio**  
  https://www.youtube.com/watch?v=VnH9gFZvj-A

- **Next.js + S3 Uploads – JavaScript Mastery**  
  https://www.youtube.com/watch?v=GqkY0v_Aq5g

---

### 🎥 Payments
- **Stripe + Next.js – Antonio**  
  https://www.youtube.com/watch?v=2v-bk5fXg7A

---

### 🎥 Testing
- **React Testing Library – Net Ninja**  
  https://www.youtube.com/watch?v=8Xb8o0ofEpw

- **Playwright Crash Course – Fireship**  
  https://www.youtube.com/watch?v=9xgJpZ1gIQk

---

### 🎥 Deployment
- **Deploy Next.js to Vercel – JavaScript Mastery**  
  https://www.youtube.com/watch?v=UfSj2RGjDx8

- **Dockerize Next.js – Devistry**  
  https://www.youtube.com/watch?v=MTj4FMk16xg

---
