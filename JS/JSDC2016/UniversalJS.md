# Universal JS
> best practice for SPA

---

# SPA
> Single Page Application

- corn: load performance

---

# Not suitable
- time dependent page
- SEO
- First time render

---

# Framework Merge
- Componentlize
  - react, vue, angular
- Signle Data Flow
  - Vuex, Flux
- Css class scope
  - css module, web compoent, .vue scoped
- Virtural DOM
  - react, Vue 2,
  - Native app
  - Server side render

---

# Advantage
- first time server render
- and SPA forever

---

# Step by Steps
1. router (server render as client render)
2. AJAX (In server side must check the AJAX data back)
  - static
  - onenter method (suggestion)
  - universal router
3. Data sync
  - set up initial state
4. static files
  - webpack boundle (suggestion)
    - webpack config
  - truely static

---

# Pain point
- View - backend vs fontend
  - data vs visual compoent
- CSS render critical path
  - `isomorphic-style-loader`
