sy-base.ntpd
=========

Simple role to manage ntpd configuration

Requirements
------------

This role has no additional requirements.

Role Variables
--------------
```
state - String value [present/absent]. present installs ntpd, absent uninstalls ntpd. Default: present
ntpd_service - String value with name of ntp service. Default: ntpd
ntpd_driftfile - String value with absolute path to ntp drift file. Default: /var/lib/ntp/drift
ntpd_servers - Dict value containing entries that should reside in your system's ntp configuration. Default:

ntpd_servers:
  - "0.pool.ntp.org iburst"
  - "1.pool.ntp.org iburst"
  - "2.pool.ntp.org iburst"
  - "3.pool.ntp.org iburst"

```

Dependencies
------------

No Dependencies.

Example Playbook
----------------
```yaml
---
- hosts: servers
  tasks:
    - include_role:
        name: sy-base.ntpd
      vars:
        state: present
        ntpd_service: ntpd
        ntpd_driftfile: /var/lib/ntp/drift
        ntpd_servers:
          - "0.pool.ntp.org iburst"
          - "1.pool.ntp.org iburst"
          - "2.pool.ntp.org iburst"
          - "3.pool.ntp.org iburst"


```

License
-------

BSD

Author Information
------------------

sybase - https://github.com/sy-base
