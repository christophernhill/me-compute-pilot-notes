# me-compute-pilot-notes
Easily updated notes and examples for me computing pilot

## Simple command to launch an interactive shell with 1 core on 1 node and 1G of memory

```
srun -p sched_mit_hill --reservation="me-computing-pilot" --pty -I /bin/bash
```

## To request a whole node for exclusive access for 12 hours

```
srun -p sched_mit_hill --reservation="me-computing-pilot" --mem=0 -N 1 --exclusive -t 12:00:00 --pty /bin/bash
```

## To run a simple batch job

```
cat > testjob.slurm <<'EOF'
echo $SLURM_JOBID
EOF

sbatch -p sched_mit_hill --reservation="me-computing-pilot" --mem=0 -N 1 --exclusive -t 1:00:00 testjob.slurm
```
