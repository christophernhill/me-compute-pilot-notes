# me-compute-pilot-notes
Easily updated notes and examples for me computing pilot

## Simplest command to launch an interactive shell with 1 core on 1 node and 1G of memory

```
srun -p sched_mit_hill --reservation="me-computing-pilot" --pty -I /bin/bash
```
