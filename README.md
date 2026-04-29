<!-- This was created with Claude Code -->

# Citrix Automation

[![Contribute](https://img.shields.io/badge/OpenShift-Dev%20Spaces-525C86?logo=redhatopenshift&labelColor=EE0000)](https://devspaces.apps.ocp.shadowman.dev/#https://github.com/shadowman-lab/Ansible-Citrix)


This directory contains Ansible automation for citrix management and operations.

## Overview

The Citrix automation provides playbooks and roles for managing and configuring
citrix infrastructure and services.

## Roles

| Role | Description |
| ---- | ----------- |
| [citrix_add](roles/citrix_add/README.md) | Role for citrix add |
| [citrix_add_dr](roles/citrix_add_dr/README.md) | Role for citrix add dr |
| [citrix_disable](roles/citrix_disable/README.md) | Role for citrix disable |
| [citrix_email](roles/citrix_email/README.md) | Role for citrix email |
| [citrix_enable](roles/citrix_enable/README.md) | Role for citrix enable |
| [citrix_remove](roles/citrix_remove/README.md) | Role for citrix remove |
| [citrix_remove_sg_dr](roles/citrix_remove_sg_dr/README.md) | Role for citrix remove sg dr |
| [citrix_remove_vs](roles/citrix_remove_vs/README.md) | Role for citrix remove vs |

## Playbooks

| Playbook | Description | Target Hosts |
| -------- | ----------- | ------------ |
| add_to_load_balancer.yml | Playbook for add to load balancer | {{ vm_name | default('all') }}, localhost |
| disable_server.yml | Playbook for disable server | {{ vm_name | default('all') }} |
| dr_add.yml | Playbook for dr add | all |
| dr_remove.yml | Playbook for dr remove | all |
| enable_server.yml | Playbook for enable server | {{ vm_name | default('all') }} |
| remove_from_load_balancer.yml | Playbook for remove from load balancer | {{ vm_name | default('all') }} |
| remove_virtual_server.yml | Playbook for remove virtual server | localhost |

## Usage

### Running with ansible-navigator

```bash
# Run a playbook
ansible-navigator run add_to_load_balancer.yml

# Run in stdout mode
ansible-navigator run add_to_load_balancer.yml -m stdout
```

### Using roles

```yaml
- hosts: target_hosts
  roles:
    - citrix_add
```

## Requirements

- Ansible 2.9 or higher (via ansible-navigator)
- Required collections (see `collections/requirements.yml` if present)
- Appropriate access credentials configured via environment variables

## Directory Structure

```
Ansible-Citrix/
├── roles/              # Ansible roles
├── *.yml               # Playbooks
├── collections/        # Collection dependencies (if present)
└── ansible-navigator.yml  # Navigator configuration
```
