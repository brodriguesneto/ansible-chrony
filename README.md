chrony
======

[![Build Status](https://travis-ci.org/brodriguesneto/ansible-chrony.svg?branch=master)](https://travis-ci.org/brodriguesneto/ansible-chrony)
[![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-brodriguesneto.ansible_chrony-blue.svg)](https://galaxy.ansible.com/brodriguesneto/ansible_chrony)

An Ansible role that installs and configures [Chrony] service on Linux and sets Timezone.

chrony is a versatile implementation of the Network Time Protocol (NTP). It can synchronise the system clock with NTP servers, reference clocks (e.g. GPS receiver), and manual input using wristwatch and keyboard. It can also operate as an NTPv4 (RFC 5905) server and peer to provide a time service to other computers in the network

Platforms
---------

Role tested on Linux operating systems:

* Ubuntu Server 18.04 LTS
* Ubuntu Server 16.04 LTS

Requirements
------------

None.

Role Variables
--------------

__chrony_servers__: The chrony pool servers to synchronize from with its default value.

```YAML
chrony_servers:
  - a.ntp.br
  - b.ntp.br
  - c.ntp.br
```

__chrony_timezone__: The Timezone to configure system-wide with its default value.

```YAML
chrony_timezone: America/Sao_Paulo
```

> The cron service will be reloaded every time the Timezone changes.

Dependencies
------------

None.

Example Playbook
----------------

```YAML
- hosts: all
  become: True
  roles:
  - role: brodriguesneto.ansible_chrony
    chrony_timezone: America/Sao_Paulo
    chrony_servers:
      - 0.br.pool.chrony.org
      - 1.br.pool.chrony.org
      - 2.br.pool.chrony.org
```

License
-------

[Apache License 2.0]

Author Information
------------------

[Boaventura Rodrigues Neto]

[Chrony]: https://chrony.tuxfamily.org/
[Cron]: https://en.wikipedia.org/wiki/Cron
[Apache License 2.0]: https://github.com/everproven/ansible-chrony/blob/master/LICENSE
[Boaventura Rodrigues Neto]: https://www.linkedin.com/in/brodriguesneto/
