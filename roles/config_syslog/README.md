# Configure Syslog

Configure syslog settings. The template under templates/eos_syslog.j2 will create a list of commands and compare it to the current commands. If the "enforce_comliance" var is set to yes, it will remove any command that does not match the commands that are declared.

An example command output is shown at the top of the template for comparison purposes.

## Role Variables

- **syslog_servers**: List of syslog servers to configure
- **syslog_port**: The port used to send logs.
- **syslog_vrf**: The VRF to use to send logs. If left empty it will use the global route table
- **syslog_source_interface**: The interface to source the syslogs from

## Example Playbook

```
- name: Configure Syslog
  hosts: all
  gather_facts: no

  roles:
    - config_syslog
```
