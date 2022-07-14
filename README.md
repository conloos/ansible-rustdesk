# Ansible role for building and running awx.
============================================

**summary**
This role is for building and running rustdesk. 
Look in the tasks directory for each configuration.
All configurations are held atomically via their own files.

## Variables that have to be defined

| variable | description | mandantory |
| -------- | ----------- | ---------- |
| rustdesk.hbbs_data_dir | Path to store persistent hbbs data | false |
| rustdesk.server_version_tag | docker Version Tag | false |
| rustdesk_public_address | docker Version Tag | true |
| rustdesk_recreate_container_and_keys | recreate the container and keys | false |

# example playbook
```
---
- hosts: 
    - example.com
  become: true
  vars:
    rustdesk_public_address: example.com
  vars_files:
    - group_vars/vault.yml
  tasks:
  roles:
    - rustdesk
```
