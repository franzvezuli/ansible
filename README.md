# Ansible Playbooks

### First Time Setup
Run `script/setup` to setup a new Mac OS X machine with all tools and applications installed.

### Updating Applications
Run `script/update` to update all installed applications.

This will take longer than running `script/setup` because it checks for updates for all installed applications.

### Implementation

The project is structured with modular shell scripts to handle environment preparation and Ansible for system configuration.

- **`script/setup`**: The entry point for initial machine setup.
- **`script/update`**: The entry point for updating existing applications and Ansible.
- **`script/osx`**: Contains macOS-specific dependency installation (`brew`, `pipx`).
- **`script/ansible`**: Contains shared Ansible-related tasks (`pipx_ensurepath`, `install_ansible`, `run_setup_playbook`, `run_update_playbook`).
- **`script/echo`**: Utility functions for color-coded output.

#### Control Flow

```mermaid
graph TD
    A[Start] --> B{Which script?}
    B -- setup --> C[script/setup]
    B -- update --> D[script/update]

    subgraph "Setup Flow"
    C --> C1{Is macOS?}
    C1 -- Yes --> C2[install_osx_dependencies]
    C2 --> C2a[install_brew]
    C2 --> C2b[install_pipx]
    C1 -- No --> C3[pipx_ensurepath]
    C2b --> C3
    C3 --> C4[install_ansible]
    C4 --> C5[run_setup_playbook]
    C5 --> C6[ansible-playbook main.yml]
    end

    subgraph "Update Flow"
    D --> D1[upgrade_ansible]
    D1 --> D2[run_update_playbook]
    D2 --> D3[ansible-playbook main.yml -e upgrade_apps=true]
    end

    C6 --> E[End]
    D3 --> E
```
