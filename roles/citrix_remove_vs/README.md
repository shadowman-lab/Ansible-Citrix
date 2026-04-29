<!-- This was created with Claude Code -->

citrix_remove_vs
================

An Ansible role for citrix remove vs.

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **virtual_server_fqdn**: Server configuration
  - Default: `citrixlb.shadowman.dev`

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: citrix_remove_vs
      vars:
        virtual_server_fqdn: <value>
```

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

Red Hat Ansible Automation Platform
