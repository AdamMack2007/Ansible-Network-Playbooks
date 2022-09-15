# Config HA

Used to configure HA peering on devices.

## Role Variables

For F5 configurations, the following vars are required:

- f5_ha_vlan = The VLAN to be used for HA replication
- f5_ha_ports = List of interface ports used for HA Port Channel
- f5_ha_primary_ip = HA Self IP for primary(active) node
- f5_ha_secondary_ip = HA Self IP for secondary(standby) node
- primary = yes or no value to determine which node will be primary
- ha_peer = name of the peer node, the playbook will reference the ansible_host variable of the peer so it must exist in inventory.
