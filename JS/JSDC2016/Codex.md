# CodexJs
speaker: Alex
> module bundler  
> build conditional bundle

---
# How to conditional bundle
truths -> require
```js
if(truths.somecondition){
  require(some_js)
}else{
  require(other_js)
}
```

---

# Request
> git -[artifact: json]-> Codex  
> user -[reqest: .js]-> CDN -[conditional: json]-> Codex Bundler

response < 80ms

---

# Scaling
- levelDB not memeory for js file
- Parsing JSON.parse is CPU costing and blocks
  - use LRU Cache

---

# Version service and API
> /**1.0.0**/API/**v1**/resource  

---
# Guildline
1. do NOT **optimize** before knowing the system.
2. use scientfic method
  - collect data **First**
