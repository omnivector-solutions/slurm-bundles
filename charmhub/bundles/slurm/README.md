# Welcome to the SLURM Bundle
This bundle provisions a minimal slurm deployment consisting of; slurmdbd
slurmctld, slurmd and percona-cluster.

## Usage
Assuming you have `juju` installed, simply run:
```bash
juju deploy slurm
```

For lxd based deployments you will need to set the `proctrack-type="proctrack/linuxproc"`
parameter in the slurmctld charm.

To do this using an overlay, create the overlay config and then use it in the deploy command.

Create the overlay file.
```bash
cat << EOY > /tmp/slurm-overlay.yaml
applications:
  slurmctld:
    options:
      proctrack-type: "proctrack/linuxproc"
EOF
```

Use the overlay file in the deploy command.
```bash
juju deploy slurm --overlay /tmp/slurm-overlay.yaml
```
