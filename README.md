# maybe-sunny-infrastructure
Infrastructure config for my hetzner stuff

## PVC storage

I have manually created a [Hetzner
volume](https://docs.hetzner.com/cloud/volumes/overview/), and mounted it (with
an `fstab` entry) in `/var/lib/rancher/k3s/storage`. This is where the PVCs are
stored by default by the [local-path
provisioner](https://github.com/rancher/local-path-provisioner) that k3s sets up
by default. This keeps the data in the various PVCs safe regardless of the node
itself surviving.