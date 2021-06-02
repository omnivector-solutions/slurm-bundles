# Welcome to the SLURM Bundle
This bundle provisions a minimal slurm deployment consisting of; slurmdbd
slurmctld, slurmd and percona-cluster.

## Usage
Assuming you have `juju` installed, simply run:
```bash
juju deploy slurm
```

For lxd based deployments you will need to set the `proctrack-type="proctrack/linuxproc"`.
Follow the deploy command above:
```bash
juju config slurmctld proctrack-type="proctrack/linuxproc"
```
