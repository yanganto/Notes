# Info Sec Sharing
> How to write the safe code in web application
> SDLC

---

# Scan
- monthly
  - system - Nessus
  - Virus
  - patch - Shavlik
  - R/W folder - script via Samba
  - Weak Password Scan - Medusa
  - Port Scan - Nmap

---

# Security Scan
- Web application
  - login
  - crawling
  - testing - special chars
  - response
  - analyze
  - **following can not automation by tool**
  - **delete admin**
  - **missing access control**
- system
- DB

---

# Web Vulnerabilites
> owasp

- XSS
  - filter both input and output
  - avoid `< > ( ) "`

- SQL injection
  - user prepared statements and stored procedures
  - SQL injection cheat sheet

- Directory Traversal
  - `../`
  - `./`
  - prevent `. / % |`

---

# before Scan
- disable account limitation
- disable reCapcha
- remove log
- DB, VM backup

---
