# Network Configuration Management

Ansible network roles to perform a base configuration of the following network devices:

- Arista EOS
- Cisco ASA
- Cisco Catalyst
- Cisco Nexus
- F5 BigIP
- Palo Alto

## Usage

Any role with config\_\* will make configuration changes to the device.

Role name and functions:

- **config_aaa**: Configure authentication/authorization settings on devices.
- **config_acl**: Configures management ACLs
- **config_backup**: Backup network devices to GIT
- **config_credentials**: Update user credentials for local accounts
- **config_dns**: Configures DNS servers
- **config_ha**: Configures HA settings
- **config_interfaces**: Configures network interfaces
- **config_ntp**: Configures NTP servers
- **config_provisioning**: Configures misc changes: hostnames, ssh ciphers, enabling API and login banners.
- **config_routing**: Configures BGP/OSPF on devices
- **config_save**: Simple playbook to save the running configurations.
- **config_snmp**: Configures SNMPv3 on devices.
- **config_syslog**: Configures remote/local syslog settings.
- **device_upgrade**: Upgrades device OS
- **facts**: Gather facts for devices

## Information

Each role has a readme with the variables or information required as well as any recommendations.

## Example playbook

Configure just NTP servers

```
- name: Configure NTP Servers
  hosts: all
  gather_facts: no

  roles:
    - config_ntp
```

Include all roles to build the entire base configuration

```
- name: Arista Base Configuration
  hosts: all
  gather_facts: no

  roles:
    - facts
    - config_provisioning
    - config_dns
    - config_ntp
    - config_snmp
    - config_syslog
    - config_credentials
    - config_aaa
    - config_save
```

## Recommendations

I strongly recommend testing in a lab first to ensure the changes comply with your desired state.
