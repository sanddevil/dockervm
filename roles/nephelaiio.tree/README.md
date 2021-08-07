# nephelaiio.tree

[![Build Status](https://github.com/nephelaiio/ansible-role-tree/workflows/CI/badge.svg)](https://github.com/nephelaiio/ansible-role-tree/actions)
[![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-nephelaiio.tree-blue.svg)](https://galaxy.ansible.com/nephelaiio/tree/)

An [ansible role](https://galaxy.ansible.com/nephelaiio/tree) to install and configure tree

## Role Variables

Please refer to the [defaults file](/defaults/main.yml) for an up to date list of input parameters.

## Example Playbook

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```
    - hosts: servers
      roles:
         - role: tree
```

## Testing

Role is tested against the following distributions (docker images):
  * Ubuntu Focal
  * Ubuntu Bionic
  * Ubuntu Xenial
  * Debian Buster
  * CentOS 7

You can test the role directly from sources using command ` molecule test `

## License

This project is licensed under the terms of the [MIT License](/LICENSE)
