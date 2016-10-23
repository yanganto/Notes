# OTP is dead and U2F comes
speacker: Vincent

---

# What is U2F ?
> user <-> user agent <---> Server

- who is server?
  - By CA
- who is user?
  - By Password -> hash checking

---

# Traditional Password
- prop
  - ez to use and know

- corn
  - expose every where
  - not normalize
  - password repeating
  - easy to phish

---

# Password Manager
- corn
  - not normalize with lots of dirty hack

---

# 2-FA
> must have **2** credential

- usually by SMS
  - prop: ez to use and known
  - corn: additional fee, rely on SMS network, bad UX
  - NIST not recommadation

- TOTP
  - prop: hight security
  - corn: bad UX, ez to phish

---

# Security Issue
- personal information (majority)
- beat the service
- getting info from service

---

# FIDO
> Fast Identity Online  

- U2F, UAF, W3C working draft

- U2F
  - private key not leave local
  - web orgin
  - different web with different key pair
  - only Chrome, Firefox (may be ready in 2017)

- use phsical push

---

#FIDO document
- Overview
- JS API
- Raw msg
- google/u2f-ref-code
- `chrome --show-component-extsion-`
