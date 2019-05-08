[![License](https://img.shields.io/badge/license-Apache%202-blue.svg)](https://www.apache.org/licenses/LICENSE-2.0)
[![Build Status](https://travis-ci.org/grycap/ansible-role-nat.svg?branch=master)](https://travis-ci.org/grycap/ansible-role-nat)

NAT server/client Role
=======================

Install NAT server/client.

Role Variables
--------------

The variables that can be passed to this role and a brief description about them are as follows.

    # Type of node to install: front or wn
    nat_mode: "front"
    # WAN Network interface in the front node
    nat_iface_wan: "eth0"
    # LAN Network interface in the front node
    nat_iface_lan: "eth1"
    # LAN newtwork CIDR
    nat_network_lan: "10.0.0.0/8"
    # Front-end IP to set as default gateway in the wn
    nat_gateway_ip: "10.0.0.1"

Example Playbook
----------------
```
  - hosts: server
  roles:
  - { role: 'grycap.nat', nat_mode: 'front', nat_iface_wan: 'eth0',  nat_iface_lan: 'eth1', nat_network_lan: '10.0.0.0/8'}
```
```
  - hosts: client
  roles:
  - { role: 'grycap.nfs', nat_mode: 'wn', nat_gateway_ip: '10.0.0.1' }
```

Contributing to the role
========================
In order to keep the code clean, pushing changes to the master branch has been disabled. If you want to contribute, you have to create a branch, upload your changes and then create a pull request.  
Thanks
