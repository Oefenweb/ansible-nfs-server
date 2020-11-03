## nfs-server

[![Build Status](https://travis-ci.org/Oefenweb/ansible-nfs-server.svg?branch=master)](https://travis-ci.org/Oefenweb/ansible-nfs-server)
[![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-nfs-server-blue.svg)](https://galaxy.ansible.com/Oefenweb/nfs-server/)

Set up NFS in Debian-like systems.

#### Requirements

None

#### Variables

* `nfs_server_service_state`: [default: `started`]: The state of th service (e.g. `stopped`)
* `nfs_server_service_enabled`: [default: `true`]: Whether the service should start on boot

* `nfs_server_etc_default_domain_suffix`: [optional]: Specifies the domain which hosts read from the DHCP leases file must have to be legal (e.g. `dnsdomainname`)
* `nfs_server_etc_default_nfs_server_opts`: [optional]: Options to pass to the `dnsmasq` daemon (e.g. `--conf-file=/etc/dnsmasq.alt`)
* `nfs_server_etc_default_config_dir`: [default: `/etc/dnsmasq.d,.dpkg-dist,.dpkg-old,.dpkg-new`]: Searches this drop directory for configuration options (leave empty to comment out)
* `nfs_server_etc_default_ignore_resolvconf`: [optional]: If the `resolvconf` package is installed, `dnsmasq` will use its output rather than the contents of `/etc/resolv.conf` to find upstream nameservers (e.g. `true`)

* `nfs_server_etc_default`: [see: `defaults/main.yml`]: List of lines to be added to `/etc/default/dnsmasq`

* `nfs_server_nfs_server_conf`: [default: `[]`]: List of lines to be added to `/etc/dnsmasq.conf`

* `nfs_server_nfs_server_d_files_present`: [default: `{}`]: Declaration of specific configuration files (to add)
* `nfs_server_nfs_server_d_files_present.key`: [required]: The name of the configuration file (e.g. `hosts`)
* `nfs_server_nfs_server_d_files_present.key.{n}`: [default: `[]`]: List of lines of the configuration file

* `nfs_server_nfs_server_d_files_absent`: [default: `{}`]: Specific configuration files to remove
* `nfs_server_nfs_server_d_files_absent.key`: [required]: The name of the configuration file (e.g. `hosts`)

## Dependencies

None

#### Example

```yaml
---
- hosts: all
  roles:
    - nfs-server
```

#### License

MIT

#### Author Information

* Mischa ter Smitten

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Oefenweb/ansible-nfs-server/issues)!
