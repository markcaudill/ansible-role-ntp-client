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

- `ntp_client_config_servers` is the list of servers to configured
    - Example:
      ```yaml
      - hostname: 0.pool.ntp.org
          options:
          - iburst
      - hostname: 1.pool.ntp.org
         options:
         - iburst
      ```
- `ntp_client_config_pools` is the list of pools to configure
    - Example:
      ```yaml
	  - hostname: 2.centos.pool.ntp.org
	      options:
	      - iburst
      ```

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
