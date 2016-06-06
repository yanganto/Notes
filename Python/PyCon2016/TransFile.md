Speak in Taiwaness

Adaptive streaming Encoding Workflow
---
- check
- transcode
- package

Current Solution
---
- Gearman - a job server
  - worker viewpoint - __hard maintain__
- Luigi
  - task viewpoint - __hard maintain__

Mass
---
source on github open by KKBOX
- viewpoint can be Job, Task, Action
- Job (Encoding Workflow)
  - Task (transcode)
    - Action
    - Subtask (1080p, 720p ...)
* easy to use with shell
- LogHandler, Slacker

Future Work
---
- AWS lambda
- exact Exception Type
- Notification wile Job/Task/Cmd start/end
- View
