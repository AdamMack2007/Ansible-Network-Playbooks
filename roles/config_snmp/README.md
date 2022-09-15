# Configure SNMP

Configures SNMP with a focus on SNMPv3. This role will check against the existing configuration and remove any SNMP configuration that is not in compliance!

## Role Variables

See defaults/main.yml for examples and notes

- **snmp_servers**: List of SNMP servers to configure
- **snmp_vrf**: The VRF to use for routing. If empty it will use the global routing table. This example has "management" VRF configured and used.
- **snmp_group**: Group name to give when configuring SNMP on the device
- **snmp_user**: Username to configure for snmpv3 auth.
- **snmp_password**: Password to configure for snmpv3 auth. Recommended to vault this!

## Example Playbook

```
- name: Configure SNMP
  hosts: all
  gather_facts: no

  roles:
    - config_snmp
```
