Hardware disk attached to EC2 instance, *not* a network drive, like EBS Volumes.

> EC2 instance stores are higher performance storage for EC2 instance that are attached to the instance and aren't network drives

- Better I/O performenace
- EC2 instance termination will lose the disk (ephemeral)
- Not for long term storage, instead use EBS
- Backups are your responsibility
