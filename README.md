ntp-client
==========

NTP client installation and configuration for Linux

Requirements
------------

So far, this is just tested on CentOS/RHEL 7 but should work on any distro with some modificaitons of the variables.

Role Variables
--------------

These are the role variables and their default values.

`ntp_client_packages` is a list of packages to install in support of this role.

```yaml
ntp_client_packages:
  - chrony
```

`ntp_client_service` describes the service and its desired state.

```yaml
ntp_client_service:
  name: chronyd
  state: started
  enabled: yes
```

`ntp_client_config` defines the configuration template to use as well as the location on the target host.

```yaml
ntp_client_config:
  src: etc/chrony.conf.j2
  dest: /etc/chrony.conf
```

`ntp_client_timezone`, while not strictly related to NTP, is used to set the timezone on the target host.

```yaml
ntp_client_timezone: Etc/UTC
```

`ntp_client_time_sources` is a list of time sources to use. Each source is rendered in the template as `type address options` as outlined in the time sources section of [the man page](https://chrony.tuxfamily.org/doc/3.4/chrony.conf.html).

```yaml
ntp_client_time_sources:
  - type: server
    address: 0.pool.ntp.org
    options: iburst
  - type: server
    address: 1.pool.ntp.org
    options: iburst
  - type: server
    address: 2.pool.ntp.org
    options: iburst
  - type: server
    address: 3.pool.ntp.org
    options: iburst
```

Dependencies
------------

None

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
