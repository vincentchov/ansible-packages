ansible-packages
================

This role allows you to specify how to add APT repos and which packages
to install for Debian, Linux Mint, and Linux Mint Debian Edition.
The primary use-case would be for when you're setting up a new desktop
computer and would like to install some applications that you can't just
`apt install` right away.

This role is originally intended for my own personal use and is used on
localhost (directly on the computer intended to be set-up.  It currently
targets Debian Buster (stable), Linux Mint 19.3, and Linux Mint Debian
Edition 3.

Requirements
------------

Debian 10, Linux Mint 19.3, or Linux Mint Debian Edition 3 on the target
machine.

Role Variables
--------------

The variables in `defaults/main.yml` outline APT configuration information
for the Linux distributions I intend to support (distro codename, repo
mirror URLs, etc).

Dependencies
------------

Currently none.

Example Playbook
----------------

Assuming you have your variable overrides in a
`vars_files/vincentchov.packages/overrides.yml` file, and assuming you have
a "local" hosts group set up as:

```ini
[local]
localhost ansible_connection=local
```

Example playbook:

```yaml
---
- hosts: local
  become: true
  roles:
     - vincentchov.packages
  vars_files:
     - vars_files/vincentchov.packages/overrides.yml
```

License
-------

GPL-3.0 or later

Author Information
------------------

My name is Vincent Chov and my personal website is at
[vincentchov.com](https://www.vincentchov.com).
