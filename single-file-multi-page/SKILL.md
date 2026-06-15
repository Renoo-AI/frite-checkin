---
name: single-file-multi-page
description: Technical architecture for compiling large multi-page applications into a single production-ready HTML file. Use this skill when a user requests multiple views, comprehensive dashboards, or full e-commerce flows (e.g., landing page, menu, builder, cart) wrapped cleanly inside one standalone execution context without external state library dependencies.
---

# Single-File Multi-Page Architecture Skill

This skill governs the production of clean Single Page Applications (SPAs) delivered via a standalone HTML file. It handles dynamic state switching, seamless views rendering, and avoids broken tutorial-grade code snippets.

## 1. Navigation Infrastructure (State-Driven Views)
- Avoid reloading or routing queries that fail locally. Use a declarative, state-driven switching approach.
- Maintain a global active view state using lightweight Vanilla JS or inline React ecosystem mapping:
```javascript
  const state = {
    currentView: 'landing',
    cart: [],
    // ... global application data
  };
  function switchView(viewId) {
    document.querySelectorAll('[data-view]').forEach(el => el.classList.add('hidden'));
    document.querySelector(`[data-view="${viewId}"]`).classList.remove('hidden');
    state.currentView = viewId;
    window.scrollTo({ top: 0, behavior: 'smooth' });
  }

```

## 2. Mandatory Structural Layout for Multi-Views

Every comprehensive standalone bundle must partition its template cleanly inside separate `<section>` tags using data attributes:

```html
<!-- Main Application Shell -->
<main class="min-h-screen bg-[#FAF8F5]">
  <!-- Persistent Navigation Header -->
  <nav class="border-b-4 border-[#1A1A1A] sticky top-0 bg-white z-50">...</nav>

  <!-- Views Layer -->
  <section data-view="landing" class="">...</section>
  <section data-view="menu" class="hidden">...</section>
  <section data-view="builder" class="hidden">...</section>
  <!-- ... remaining views -->
</main>

```

## 3. Production Integrity Bar

* **NO PLACEHOLDERS:** Do not write comments like `<!-- Rest of the menu items here -->`. Complete every block. If a list of cards or interactive itemizers is declared, populate them fully with rich contextual copy and complete assets mock-up data.
* **Dynamic Interactions:** All modular views must communicate natively (e.g., clicking a product card in the `menu` view must update the floating numbers on the main navigation and push state records directly into the itemized `cart` sidebar/view).
