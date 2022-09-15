# Configure DNS

Configure DNS servers and lookup information

## Role Variables

- **dns_servers**: List of DNS servers to configure
- **dns_vrf**: VRF to use for DNS lookups. If left empty will use global routing table.
- **dns_source_interface**: Interface to use for DNS lookups.

## Example Playbook

```
- name: Configure DNS
  hosts: all
  gather_facts: no

  roles:
    - config_dns
```
