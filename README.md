<p><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/0/0c/Logo_Hetzner.svg/2000px-Logo_Hetzner.svg.png" alt="hetzner logo" title="hetzner" align="right" height="60" /></p>

Ansible Role: Hetzner
=====================

[![Build Status](https://ci.devops.sosoftware.pl/buildStatus/icon?job=SoInteractive/hetzner/master)](https://ci.devops.sosoftware.pl/blue/organizations/jenkins/SoInteractive%2Fhetzner/activity) [![License](https://img.shields.io/badge/license-MIT%20License-brightgreen.svg)](https://opensource.org/licenses/MIT) [![Ansible Role](https://img.shields.io/ansible/role/18270.svg)](https://galaxy.ansible.com/SoInteractive/hetzner/) [![Twitter URL](https://img.shields.io/twitter/follow/sointeractive.svg?style=social&label=Follow%20%40SoInteractive)](https://twitter.com/sointeractive)

Role will partition disks and install Ubuntu 16.04 (default) or CentOS7

Disclaimer
----------

Automated tests aren't possible

Requirements
------------

Server in rescue mode.

Example usage
-------------

Use it in a playbook as follows:
```yaml
- hosts: all
  become: true
  roles:
    - SoInteractive.hetzner
```

Have a look at the [defaults/main.yml](defaults/main.yml) for role variables
that can be overridden.
