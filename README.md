Fully provision new physical server in Hetzer DC
================================================

Role will partition disks and install Ubuntu 16.04 (default) or CentOS7

Disclaimer
----------

Automated tests aren't possible

Requirements
------------

Server in rescue mode.

Examples
--------

Use it in a playbook as follows:
```yaml
- hosts: all
  become: true
  roles:
    - hetzner-provision 
```

Have a look at the [defaults/main.yml](defaults/main.yml) for role variables
that can be overridden.
