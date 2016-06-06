Jupyter, IPython
---
- what's different
  - Ipython is python enhance with shell
    - Interactive Python shell
    - Auto Word Completer
    - Beatiful Traceback
    - Shell History
    - Magic Command

  - Jupyter - Julia, Python, R
      - can swithch with different kernel

Jupyter
---
default use ipykernel   
client <-0MQ sockets-> kernel   
2 client with 1 kernel

Jupyter Messaging Protocol
---
base on 0MQ(5 sockets) and Json  
- shell socket - Dealer <-shell-> router
- IOPub - Sub <-IOPub- Pub
- STDIN - Dealer <-STDIN- router
- Control - Dealer -Control-> Router
- Heartbeat - REQ <-Heartbeat-> REP  

[message](http://jupyter-client.readthedocs.io/en/latest/messaging.html)


Implementing a Kernel
---
Type
  - Native
  - Python Wrapper Kernel
    - in [IPykernel](http://bit.ly/WrapperKernel)
      - implement do_execute ...
  - REPL Wrapper Kernel
    - ` from pexpect.replwrap import REPLWrapper`
    - Implement with shell

Implement a Kernel
---
