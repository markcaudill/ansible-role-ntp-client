ntp_client
==========

NTP client installation and configuration for Linux

[![CI](https://github.com/markcaudill/ansible-role-ntp-client/workflows/CI/badge.svg)](https://github.com/markcaudill/ansible-role-ntp-client/actions?query=workflow%3ACI)

Requirements
------------

So far, this is just tested on CentOS/RHEL 7 and 8 but should work on any distro with some modificaitons of the variables.

Role Variables
--------------

See (`defaults/main.yml` for a complete listing).

- `ntp_client['packages']`: a list of packages installed (default: `[chrony]`)
- `ntp_client['service']`: the service/daemon configuration (default: `chronyd`, started and enabled on boot)
- `ntp_client['timezone']`: the timezone to use for the system (this isn't directly NTP-related) (default: `Etc/UTC`)
- `ntp_client['config']`: the variables used to generate the `chrony.conf` file (see `defaults/main.yml` for more detail)

Dependencies
------------

None

Installation
------------

```sh
ansible-galaxy install markcaudill.ntp_client
```

Example Playbook
----------------

    - hosts: all
      roles:
         - markcaudill.ntp_client

License
-------

MIT

Author Information
------------------

Mark Caudill <mark@mrkc.me>
