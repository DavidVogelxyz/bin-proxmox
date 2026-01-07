bin-proxmox
===========

`bin-proxmox` is a collection of Bash scripts that should be on all Proxmox servers. This repo is often deployed in conjuction with [my dotfiles](https://github.com/DavidVogelxyz/dotfiles).

Usage
-----

Within the root of this project (`bin-proxmox`) is a directory named `bin-proxmox`. Create a symlink at `${HOME}/.local/bin/bin-proxmox` that points to the *subdirectory* named `bin-proxmox`.

Table of contents
-----------------

- [Usage](#usage)
- [Scripts](#scripts)
    - [prox-dush](#prox-dush)

Scripts
-------

### prox-dush

Date created: 2025 Oct 12, Sun

`prox-dush` was written to create a utility that makes it easy to know how much disk space each VM and container is using.

The Proxmox web UI will show the total disk space used by VMs and containers, but does not show their usage. With a `ssh` connection, it's possible to run `du` against the VM disk directory to display the usage of each VM. However, this will only display the usage associated with a VM ID -- extra work is required to associate VM IDs back to the names of the VMs.

`prox-dush` solves this problem by printing a clean table of all VMs and containers, sorted from largest to smallest, and includes both the VM/container ID as well as their name.
