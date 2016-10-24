# Metaprograming in ES2015
speaker: kidwm

---

# What is Metaprograming?
1. Program transformation
  - babel
2. Dynamic excution
  - eval()
3. Introspection & Reflection
  - typeof, instaceof, delete, bind, call, apply

---

# ES2015
- symbol (not RoR, it's different)
  - new data type
  - `Symbol()`
  - use to global registry
  - **cross iframe**
  - .keyFor() to query
  - .for()
  - never conflict, but not private

- Reflect
  - new global object
  - Reflect.construnct(target, argument, newTarget=target): Object
  - Reflect.deleteProperty(target, propertyKey): bool
    - not raise error
  - Reflect.getProperty(target, propertyKey, reciver): any
  - Reflect.has(target, propertyKey): bool
  - Reflect.setProperty(target, propertyKey, value, reciver=target): any
  - Reflect.apply(target, thisArgument, argumentsList): any
  - .defineProperty(...)
  - .getOwnPropertyDescriptor(...)

- Proxy
  - global construnctor
  - `new Proxy(target, handler)`
  - object.observe: set, preventExtensions, deleteProperty, defineProperty

---
