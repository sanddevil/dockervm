andrewrothstein.docker_engine
=========
![Build Status](https://github.com/andrewrothstein/ansible-docker_engine/actions/workflows/build.yml/badge.svg)

Installs the Docker Container Engine from OS packages.

Requirements
------------

See [meta/main.yml](meta/main.yml)

Role Variables
--------------

See [defaults/main.yml](defaults/main.yml)

Dependencies
------------

See [meta/main.yml](meta/main.yml)

Example Playbook
----------------

```yml
- hosts: servers
  roles:
    - role: andrewrothstein.docker_engine
```

License
-------

MIT

Author Information
------------------

Andrew Rothstein <andrew.rothstein@gmail.com>
