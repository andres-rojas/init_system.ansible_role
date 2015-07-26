init_system
===========

This role performs initial setup for a new node.

It:

- performs a one-time apt-get upgrade
- sets the hostname to your {{ inventory_hostname }}
- SSH
    - denies password authentication
    - denies login by root
- initializes iptables
- installs fail2ban

Dependencies
------------

This role uses Stouts.timezone to set the node's timezone. It can be configured with the following variables:

```yaml
timezone_enabled: yes                   # The role is enabled
timezone_timezone: Etc/UTC              # Set timezone
```

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - init_system
  vars:
    timezone_timezone: EST5EDT
```

License
-------

Licensed under the MIT License. See the LICENSE file for details.

Author Information
------------------

- http://conpat.io
- andres@conpat.io
