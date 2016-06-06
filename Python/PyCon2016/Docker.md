CPU bound problems, solved by Celery and docker swarm

Celery - a task queue framework
---
- Producer
- Broker
  - exchange
    - queue
- Consumer
  - worker (pl)

Broker and consumer can be different PC
```
celery -A IoT worker -n neuron_h1 -Q neuron_h1 -concurrency=1
```
- profject
  - IoT
    - celery.py

```
app = Celery(...)
...
```

user docker as a node
docker swarm - a docker controller

Celery have __canvas__ to draw flow
