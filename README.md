playbook-etherpad
======================

An Ansible playbook for deploying [etherpad lite](https://github.com/ether/etherpad-lite).  
Adapted from https://github.com/p2pu/marvin/tree/master/etherpad-lite-install

## What it does
* Installs nodejs, mysql-server, nginx, etherpad-lite, and abiword.
* Configures nginx and etherpad-lite.
* Clones etherpad and configures settings.

## Requirements
* Ansible installed on client.
* Debian based distro installed on server (tested with Ubuntu 12.04).
* root username/password on server, ssh installed.

## Vars and setup
You will need to copy `group_vars/all.example` to `group_vars/all` then edit `group_vars/all`.

Also copy `hosts.example` to `hosts` and enter the ip or hostname of your server in place of the ip.

By default we try to login with root via ssh, if you have another user with sudo access on your server(e.g. Amazon) edit `install.yml` and change the user and uncomment the sudo line.

## Running the play
`ansible-playbook -k -i hosts install.yml`

Drop the -k if you are logging in with a public/private key.

`ansible-playbook -i hosts install.yml`

TODO:  
  Configure nginx SSL reverse proxy, modularize play
