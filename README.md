# Ansible Playbooks

## Table of Contents
- [First Time Setup](#first-time-setup)
- [Updating Applications](#updating-applications)
- [Implementation](#implementation)
  - [Control Flow](#control-flow)

## Scripts

The project is structured with modular shell scripts to handle environment preparation and Ansible for system configuration.

- **`script/setup`**: The entry point for initial machine setup.
- **`script/update`**: The entry point for updating Ansible itself and all installed applications.

### Helper Scripts
- **`script/osx`**: Contains macOS-specific dependency installation.
- **`script/ansible`**: Contains shared Ansible-related tasks.
- **`script/echo`**: Utility functions for color-coded output.

## Ansible Playbooks
- **`main.yml`**: The main playbook entry point.
- **`mac-setup.yml`**: The playbook for macOS-specific setup tasks.
