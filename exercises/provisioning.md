# Provisioning

We've now been running only against localhost so let's gear up.

## Goal

Setup nginx in remote machine

## Requirements

Install sshpass
`sudo apt-get update && apt-get install -y sshpass`

## Steps

1. Create new folder `provisioning` under `exercises`
2. Create `roles` folder under `provisioning`
3. Create `nginx` folder under `roles`
4. Create following folders under `nginx`
  * `files`
  * `tasks`
5. Create `main.yml` file under `roles/nginx/tasks` folder
6. Create `index.html` file under `roles/nginx/files` folder
7. Create needed tasks to copy `index.html` file to remote machine
8. Create needed tasks to deploy nginx container to remote macine with bind mount to html file and port forwarding
  * port is provided for you
  * Check builtin shell module or try to use some alternative
9. Create `hosts` inventory file with provided ip address under `provisioning`
10. Create `playbook.yml` to run `nginx` role
```
---
  - hosts: all
    roles:
```
11. Run `ansible-playbook -i hosts -u vagrant -k playbook.yml` under `provisioning` folder
12. Open browser to <provided_ip>:<provided_port> to check that your deployment was successful.


If you encouter `known_hosts` issue use ssh to login machine first
