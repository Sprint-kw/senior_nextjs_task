# Senior Front-End Developer Task (Next.js Only)

## 1. Project Overview

Build a **highly interactive and scalable social feed** interface using **Next.js**, focusing solely on front-end craftsmanship. All backend endpoints, GraphQL subscriptions, and WebSocket channels are available via provided mocks. Demonstrate mastery of modern Next.js features, performance optimization, and best-in-class developer experience.

### User Stories

1. **Feed Browsing**: As a user, I can scroll infinitely through the latest posts, see placeholders during loading, and gracefully handle end-of-feed or error states.
2. **Post Creation**: As a user, I can compose rich posts with text formatting, image upload, and emoji support, seeing a live preview as I type.
3. **Post Interactions**: As a user, I can like, comment, and see real-time reaction counts and new comments for any post.
4. **Localization & Theming**: As a user, I can switch between English and Spanish, and toggle light/dark themes, with preferences persisted.
5. **Offline Support**: As a user, I can view cached feed content and queue interactions while offline, which sync when connection returns.

---

## 2. Core Deliverables

### 2.1 Pages & Components

- **`/feed`**: Infinite-scroll list of PostCard components.
- **`/posts/[id]`**: Post detail view with CommentThread and ReactionBar components.
- **`/posts/new`**: Rich text post editor with live Markdown/HTML preview.
- **ThemeToggle**: Global light/dark mode switch.
- **LocaleSwitcher**: Switch UI text between EN/ES using i18n.

### 2.2 Architecture & Organization

- Use the Next.js **app router** (`/app`) with nested layouts and server/client components separation.
- Create a **component library** in `src/components` and document it via **Storybook**.
- Maintain a **design tokens** file (colors, spacing, typography) for consistent styling.

### 2.3 Data Fetching & State Management

- Use **GraphQL** with **Apollo Client** (or **React Query** + fetchGraphQL) for queries, mutations, and **subscriptions** (LiveFeed, NewComments).
- Implement client-side caching, optimistic UI updates, and pagination cursors.
- Persist theme and language preferences to `localStorage` and React Context.
- Use **Zustand** or **Redux Toolkit** for global UI state (theme, locale, offline queue).

### 2.4 Real-Time & Offline

- Subscribe to new posts/comments via GraphQL subscriptions or mock WebSocket connector.
- Queue interactions (likes, comments) offline with **service worker** (Workbox) and sync on reconnect.

### 2.5 Performance & SEO

- Use **Image Optimization** (`next/image`) with modern formats and placeholders.
- Implement **code splitting** and dynamic imports for heavy modules (editor, comment thread).
- Set strict **Lighthouse** performance budget: < 2s TTI on mobile.
- Use **Head** component for meta tags and open graph tags (SEO, social sharing).

### 2.6 Styling & Accessibility

- Use **Tailwind CSS** with JIT mode and custom theme via `tailwind.config.js`.
- Ensure WCAG AA compliance: ARIA roles, keyboard focus management, color contrast.
- Build accessible components (buttons, modals, dropdowns) in the component library.

### 2.7 Testing & Quality

- **Unit Tests**: Jest + React Testing Library for core components (PostCard, Editor, ThemeToggle).
- **Integration Tests**: Next.js testing with **Playwright** or **Cypress** for user flows (create post, feed scroll, offline queueing).
- Provide at least **80% coverage** on UI-critical logic.

### 2.8 Developer Experience

- Document components and hooks in **Storybook** with controls and accessibility panel.
- Lint and format with **ESLint** (including accessibility rules) and **Prettier**.

---

## 3. Bonus Challenges

- Implement **A/B testing** for two different feed layouts using **Next.js Middleware** to route a subset of users.
- Integrate **Google Analytics 4** or **Segment** for page views and interaction events.
- Add **RTL** (right-to-left) support for Arabic locale.

---

## 4. Evaluation Criteria

- **Code Organization** & Next.js best practices (app router, server/client separation).
- **Performance** metrics and optimization techniques (image, code splitting, offline support).
- **UX Quality**: polished interactions, error/loading states, accessibility.
- **Testing**: coverage, test reliability, and clarity.
- **Developer Experience**: documentation, Storybook usage, clear README.

---

# Deliverables

1. **GitHub Repo**: Public with clear commit history.
2. **Readme**: Setup, dev scripts, component library, performance reports, architecture overview.
3. **Storybook**: Hosted locally via `npm run storybook`.
4. **Test Reports**: Coverage badges and test run results.
5. **Demo**: Optional video or GIF showcasing key features (feed scrolling, theme toggle, offline sync).
