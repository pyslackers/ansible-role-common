Role Name
=========

[![Build Status](https://travis-ci.org/pyslackers/ansible-role-common.svg?branch=master)](https://travis-ci.org/pyslackers/ansible-role-common)

Base role required for servers to be configurable by ansible, with basic security measures in place

Requirements
------------

None

Role Variables
--------------

*`user`: If defined create sudo user and block root login

*`apt_cache_valid_time`: Update the apt cache if its older than the `apt_cache_valid_time`.
*`base_packages`: List of commonly required packages.
*`custom_packages`: Custom list of packages to install (default is empty).

*`github_users`: List of github users to authorized.
*`ssh_keys`: List of ssh keys to authorized.
*`ssh_port`: Ssh listen port.

Other available variables can be found in the `defaults/main.yml` file.


Example Playbook
----------------

```yml
- role: pyslackers.common
  github_users:
    - ovv
    - mrasband
  ssh_port: 2222
  ssh_keys:
    - ssh-rsa AAAAA...
  custom_packages:
    - gzip
```

License
-------

MIT

Author Information
------------------

None
