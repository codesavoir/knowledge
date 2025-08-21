# Playbook: Disk Pressure

## Detection
- Node condition: DiskPressure = True.

## Triage
- Check inode vs space usage.
- Identify largest directories (du -sh *).

## Mitigation
- Prune unused container images.
- Rotate / compress logs.
- Expand volume or migrate workloads.

## Prevention
- Set retention policies.
- Implement image GC thresholds.

> TODO: Add sample cleanup script.
