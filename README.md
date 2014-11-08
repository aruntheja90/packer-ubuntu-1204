# Packer Example - Ubuntu 12.04 minimal Vagrant Box

This example build configuration installs and configures Ubuntu 12.04 x86_64 minimal using Ansible, and then generates a Vagrant box file for use with VirtualBox.

The example can be modified to use more Ansible roles, plays, and included playbooks to fully configure (or partially) configure a box file suitable for deployment for development environments.

## Requirements

The following software must be installed/present on your local machine before you can use Packer to build the Vagrant box file:

  - [Packer](http://www.packer.io/)
  - [Vagrant](http://vagrantup.com/)
  - [VirtualBox](https://www.virtualbox.org/)
  - [Ansible](http://docs.ansible.com/intro_installation.html)

You will also need the [`geerlingguy.packer-debian`](https://galaxy.ansible.com/list#/roles/948) Ansible role installed, which can be installed using the command `ansible-galaxy install geerlingguy.packer-debian`.

If you have the role installed somewhere besides the default roles path on your machine (`/etc/ansible/roles`), you will need to edit the `role_paths` inside `ubuntu1204.json` to match the location of the `geerlingguy.packer-debian` role. If you don't have Ansible installed (perhaps you're using a Windows PC?), you can simply [clone the repository from GitHub](https://github.com/geerlingguy/ansible-role-packer-debian), and update the `role_paths` variable to match the location of the cloned role.

## Usage

Make sure all the required software (listed above) is installed, then cd to the directory containing this README.md file, and run:

    $ packer build ubuntu1204.json

After a few minutes, Packer should tell you the box was generated successfully.

## License

MIT license.

## Author Information

Created in 2014 by [Jeff Geerling](http://jeffgeerling.com/), author of [Ansible for DevOps](http://ansiblefordevops.com/).
