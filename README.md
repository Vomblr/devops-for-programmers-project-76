### Hexlet tests and linter status:
[![Actions Status](https://github.com/Vomblr/devops-for-programmers-project-76/workflows/hexlet-check/badge.svg)](https://github.com/Vomblr/devops-for-programmers-project-76/actions)


## About

This is yet another Hexlet Devops project. Deployment of a [Redmine](https://hub.docker.com/_/redmine) container with Ansible

## Link

- https://askdmitry.space

## Deployment steps

### Step 1: create VM's and accounts

- Create VM's on Yandex Cloud or DO
- Create Mysql DB Cluster 
- Create the DataDog account

### Step 2: Prepare for the deployment

- Install [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html) on your machine
- Setup cloud VM IP's in the [Inventory](./inventory.ini)
- Setup environment
  - Set common variables [vars.yml](./group_vars/all/vars.yml)
  - Same for the [webservers](./group_vars/webservers) and setup secrets in the [vault.yml](./group_vars/webservers/vault.yml)
  - Create a password in the `vault-password`. It's added to the `.gitignore`.
  - Encrypt secrets: `make encrypt`.

### Step 3: Deploy

See the [Makefile](./Makefile) for all available commands

Example: `make install setup deploy`
