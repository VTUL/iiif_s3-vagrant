# iiif_s3-vagrant
This repository enables a development environment to be set up for work
with the `iiif_s3` gem. The development environment is created using Vagrant.
It uses Ansible for provisioning and the Ansible playbook can be used as
a basis to set up alternative environments (e.g., bare metal). Vagrant,
Ansible, and VirtualBox must be installed locally for the `Vagrantfile` in
this repository to work.

The development environment created has the `iiif_s3` gem and its
prerequisites installed. This includes ImageMagick, Ruby, and Bundler.
The `iiif_s3` gem is installed system-wide.

To bring up the environment simply execute `vagrant up` in the
`iiif_s3-vagrant` repository directory. Enter the environment using
`vagrant ssh`.

Note: inside the VM environment the `/vagrant` directory is actually
a shared folder that points to the original repository directory on the host
machine. Any files there are editable from outside the development environment
VM using tools (editors, IDEs) on the host system. The `vagrant` user inside
the VM has permission to access files in the `/vagrant` shared folder.
