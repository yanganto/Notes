Talk: Strategies for concurrency and parallelism in Python
---
- data: PyCon2016 Day1 morning
- speaker:  洪鈺庭

Models
---
- synchronous model (18s)
  - one task in one time (voice to speech)
- multi-threading (5s)
  - feature provide by OS
  - share the _same_ memory
- GIL Global interpreter lock
  - prevent thread safe problem
  - multi-thread in one (provide cons w/ __I/O bound task__)
  - but __NOT__ suitable for CPU bound task
- multi-processing (~5s)
  - memory space copy
  - memory may over head when in big system
- Distributed Workers - RQ + Redis
  - high scalebility
- PaaS
  - good manage,
  - less customize

QA
---
Python3.4 ascyncio
Python3.5 coroutines (handle I/O bound)
