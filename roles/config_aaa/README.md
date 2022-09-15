# Configure AAA

Configure AAA settings on a device. This example focuses solely around TACACS.

Has the option to generate tacacs keys or to accept existing keys. If the keys doesn't exist, it will skip adding host key section and just configure the group.

## Role Variables

- **aaa_servers**: List of AAA servers to configure
- **aaa_group_name**: Name of group to nest the AAA servers under
- **aaa_key**: Key to assign to servers. Optional, set aaa_create_key:yes to generate a random one.
- **aaa_create_key**:(yes/no) If yes Ansible will create a aaa key if aaa_key is not defined. Will store it in device facts (Ansible Tower)

## Example Playbook

```
- name: Configure AAA
  hosts: all
  gather_facts: no

  roles:
    - config_aaa

```
