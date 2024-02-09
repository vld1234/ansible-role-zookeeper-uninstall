Zookeeper Uninstall
=========
[![License](https://img.shields.io/badge/license-Apache-green.svg?style=flat)](https://raw.githubusercontent.com/lean-delivery/ansible-role-zookeeper-uninstall/master/LICENSE)
[![Build Status](https://travis-ci.org/lean-delivery/ansible-role-zookeeper-uninstall.svg?branch=master)](https://travis-ci.org/lean-delivery/ansible-role-zookeeper-uninstall)
[![Build Status](https://gitlab.com/lean-delivery/ansible-role-zookeeper-uninstall/badges/master/build.svg)](https://gitlab.com/lean-delivery/ansible-role-zookeeper-uninstall/pipelines)
[![Galaxy](https://img.shields.io/badge/galaxy-lean__delivery.zookeeper__uninstall-blue.svg)](https://galaxy.ansible.com/lean_delivery/zookeeper_uninstall)
![Ansible](https://img.shields.io/ansible/role/d/40164.svg)
![Ansible](https://img.shields.io/badge/dynamic/json.svg?label=min_ansible_version&url=https%3A%2F%2Fgalaxy.ansible.com%2Fapi%2Fv1%2Froles%2F40164%2F&query=$.min_ansible_version)

## Summary

This role:
  - Uninstalls zookeeper on Centos 7, Ubuntu, Debian host

Requirements
------------
  - Minimal Version of the ansible for installation: 2.7
  - **Zookeeper installed** [![Build Status](https://travis-ci.org/lean-delivery/ansible-role-zookeeper.svg?branch=master)](https://travis-ci.org/lean-delivery/ansible-role-zookeeper)
  - **Supported OS**:
    - CentOS
      - 7
    - Ubuntu
	- Debian
	  - 9


[Prepared Windows System](https://docs.ansible.com/ansible/latest/user_guide/windows_setup.html)

## Role Variables
- `zk_version` -  version of the package

   default: `3.4.14`

 - `zk_service_name` - zookeeper service name

   default: `zookeeper`

- `zk_tarball_installation` - installation from tarball(or repository)

   default: `True`

- `zk_user` - OS user name for zookeeper

   default: `zookeeper`

- `zk_group` - OS user group name for zookeeper

   default: `zookeeper`

 - `zk_data_dir` - libraries directory

    default: `/var/lib/zookeeper`

 - `zk_log_dir` - logs directory

    default: `/var/log/zookeeper`

 - `zk_dir` - zookeeper directory

    default: `"{{ zk_tarball_installation | ternary('/opt/zookeeper-' + zk_version, '/usr/lib/zookeeper') }}"`

 - `zk_remove_user` - zookeeper user and group will be removed

    default: `False`

Example Inventory
----------------
```ini
[zookeeper]
zookeeper1.example.com
zookeeper2.example.com
zookeeper3.example.com
```

Example Playbook
----------------

```yml
- name: Uninstall zookeeper
  hosts: zookeeper
  roles:
    - role: lean_delivery.zookeeper_uninstall
```

License
-------

Apache

Author Information
------------------

authors:
  - Lean Delivery Team <team@lean-delivery.com>
