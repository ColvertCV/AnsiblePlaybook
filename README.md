# Docker Installation Ansible Playbook

This Ansible playbook checks if Docker is installed on an Ubuntu server and installs it if it's not present.

## Prerequisites

- Ansible installed on your local machine
- SSH access to the target server
- SSH private key named `server` in your current directory

## Configuration

1. Edit the `inventory` file and replace `YOUR_SERVER_IP` with your actual server IP address.

2. Make sure your SSH private key named `server` is in the same directory as the playbook.

## Usage

To run the playbook:

```bash
ansible-playbook -i inventory docker_install.yml
```

## What the Playbook Does

1. Checks if Docker is installed
2. If Docker is not installed:
   - Installs required system packages
   - Adds Docker's official GPG key
   - Adds Docker repository
   - Installs Docker CE
   - Installs Docker Python module
   - Starts and enables Docker service

## Notes

- The playbook requires sudo privileges on the target server
- Make sure your SSH key has the correct permissions (600)
- The playbook is idempotent - it can be run multiple times safely 