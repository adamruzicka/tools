# vmclone

A utility to quickly spin up virtual machines from cloud images.

## How does it work?
`vmclone` takes a cloud-init enabled disk image, creates a new disk image using the cloud-init disk image as a backing image, builds a cloud-init configuration to be used by the VM and then creates a new VM using the new disk image and generated cloud-init.

## Before first use
- install all the dependencies (see below)
- create a directory where you will create your base images (`$VMCLONE_BASE_DIR`)
- take the `cloud-init` file from this repository, copy it to `$VMCLONE_BASE_DIR`, add your ssh public keys to it
- get a cloud-init enabled disk image, place it into `$VMCLONE_BASE_DIR`
- (optional, but recommended) put `export LIBVIRT_DEFAULT_URI=qemu:///system` to your shell profile

## Actual usage
- (optional) run `vmclone -h` to see the available options
- run `vmclone` (optionally with options)
- when prompted, select a disk image
- when prompted, enter sudo password
- give the new VM a bit of time to start up
- enjoy your new VM

## Dependencies
- bash
- virt-install
- qemu-img
- fzf
- sudo
- petname (optional) - https://github.com/allenap/rust-petname

