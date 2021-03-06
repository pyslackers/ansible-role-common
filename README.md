pyslackers.common
=================

[![Build Status](https://travis-ci.org/pyslackers/ansible-role-common.svg?branch=master)](https://travis-ci.org/pyslackers/ansible-role-common)

Base role required for servers to be configurable by ansible, with basic security measures in place.

Role Variables
--------------
* `hostname_override`: Customize the hostname.
* `base_packages`: List of commonly required packages.
* `custom_packages`: Custom list of packages to install (default is empty).
* `locales`: List of locale to generate.
* `aliases`: Dict of aliases to create in .bash_aliases (some defaults provided in `default_aliases`).
* `apt_cache_valid_time`: Update the apt cache if its older than the `apt_cache_valid_time`.
* `apt_upgrade`: Update the installed packages. Support `full`, `dist` or `safe`, use `False` to deactivate (default is `safe`).
* `vim_colorscheme`: Vim colorscheme (default to `desert`).
* `vim_custom`: Custom configuration to be added to `vimrc.local`.

* `github_users`: List of github users to authorized.
* `ssh_keys`: List of ssh keys to authorized.
* `ssh_port`: Ssh listen port.

* `ufw_enabled`: Enable UFW.
* `fail2ban_enabled`: Install and enable fail2ban.
* `sysstat_enabled`: Install and enable sysstat.

* `user`: Create sudo user.
* `sftp_users`: Create user with sftp password login (the `key` is used as username).
    * `password`: User password.
    * `home`: User home directory (default to `/home/{{ user }}`).
* `root_login`: Authorize root login (default to true).

![warning](https://github.com/pyslackers/ansible-role-common/blob/master/warning.png "Warning")
Make sure to have ssh access with another user before disabling `root_login`.



Other available variables can be found in the `defaults/main.yml` file.

Example Playbook
----------------

```yml
- hosts: localhost
  vars:
    github_users:
      - ovv
      - mrasband
    ssh_port: 2222
    ssh_keys:
      - ssh-rsa AAAAA...
    custom_packages:
      - gzip
  roles: 
    - pyslackers.common
```

License
-------

MIT
