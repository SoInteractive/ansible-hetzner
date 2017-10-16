<p><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/0/0c/Logo_Hetzner.svg/2000px-Logo_Hetzner.svg.png" alt="hetzner logo" title="hetzner" align="right" height="60" /></p>

Ansible Role: Hetzner
=====================

[![Build Status](https://travis-ci.org/SoInteractive/ansible-hetzner.svg?branch=master)](https://travis-ci.org/SoInteractive/ansible-hetzner) [![License](https://img.shields.io/badge/license-MIT%20License-brightgreen.svg)](https://opensource.org/licenses/MIT) [![Ansible Role](https://img.shields.io/badge/ansible%20role-SoInteractive.hetzner-blue.svg)](https://galaxy.ansible.com/SoInteractive/hetzner/) [![GitHub tag](https://img.shields.io/github/tag/sointeractive/ansible-hetzner.svg)](https://github.com/SoInteractive/ansible-hetzner/tags) [![Twitter URL](https://img.shields.io/twitter/follow/sointeractive.svg?style=social&label=Follow%20%40SoInteractive)](https://twitter.com/sointeractive)

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
