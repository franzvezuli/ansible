# Ansible Scripts

My personal Ansible scripts for setting up or updating my machines.

## Table of Contents
- [Scripts](#scripts)
    - [Helper Scripts](#helper-scripts)
- [Ansible Playbooks](#ansible-playbooks)

## Scripts

The main entrypoints are shell scripts to simplify even the installation of Ansible itself.
- **`script/setup`**: The entry point for initial machine setup.
- **`script/update`**: The entry point for updating Ansible itself and all installed applications.

### Helper Scripts
- **`script/osx`**: Contains macOS-specific dependency installation.
- **`script/ansible`**: Contains shared Ansible-related tasks.
- **`script/echo`**: Utility functions for color-coded output.

## Ansible Playbooks
- **`main.yml`**: The main playbook entry point.
- **`mac-setup.yml`**: The playbook for macOS-specific setup tasks.
