# Config Save

Simple role to save the current running config.

## Example Playbook

```
- name: Config Save
  hosts: all
  gather_facts: no

  roles:
    - config_save
```
