# Configure Credentials

Used to configure local credentials. The option to purge all accounts that are not "admin" is configured. See the Role Variables section for the variable details.

## Role Variables

- **purge_users**: (yes/no) Whether to purge all local users that are not "admin".
- **local_pass**: The local password to configure for the admin user. Recommended to set this as a vaulted password or in Tower use a Custom Credential Type to encrypt this password.

## Example Playbook

```
- name: Configure Credentials
  hosts: all
  gather_facts: no

  roles:
    - config_credentials

```
