# me-compute-pilot-notes
Easily updated notes and examples for me computing pilot

## Simple terminal command to launch an interactive shell with 1 core on 1 node and 1G of memory

```
srun -p sched_mit_hill --reservation="me-computing-pilot" --pty -I /bin/bash
```

## Terminal command to request a whole node for exclusive access for 12 hours

```
srun -p sched_mit_hill --reservation="me-computing-pilot" --mem=0 -N 1 --exclusive -t 12:00:00 --pty /bin/bash
```

## Terminal command to run a simple batch job

```
cat > testjob.slurm <<'EOF'
#!/bin/bash
echo $SLURM_JOBID
EOF

sbatch -p sched_mit_hill --reservation="me-computing-pilot" --mem=0 -N 1 --exclusive -t 1:00:00 testjob.slurm
```
