## nfs-server

[![CI](https://github.com/Oefenweb/ansible-nfs-server/workflows/CI/badge.svg)](https://github.com/Oefenweb/ansible-nfs-server/actions?query=workflow%3ACI)
[![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-nfs--server-blue.svg)](https://galaxy.ansible.com/Oefenweb/nfs_server/)

Set up NFS in Debian-like systems (server side)

#### Requirements

None

#### Variables

* `nfs_server_service_state`: [default: `started`]: The state of th service (e.g. `stopped`)
* `nfs_server_service_enabled`: [default: `true`]: Whether the service should start on boot

* `nfs_server_etc_default_nfs_common`: [see: `defaults/main.yml`]: List of lines to be added to `/etc/default/nfs-common`
* `nfs_server_etc_default_nfs_kernel_server`: [see: `defaults/main.yml`]: List of lines to be added to `/etc/default/nfs-kernel-server`
* `nfs_server_lockd`: [see: `defaults/main.yml`]: List of lines to be added to `/etc/modprobe.d/lockd.conf`

* `nfs_server_exports`: [see: `defaults/main.yml`]: List of lines to be added to `/etc/exports`

## Dependencies

None

## Recommended

* `ansible-nfs-client` ([see](https://github.com/Oefenweb/ansible-nfs-client))

#### Example

```yaml
---
- hosts: all
  roles:
    - oefenweb.nfs-server
  vars:
    nfs_server_exports:
      - |
        /home 192.168.1.0/24(rw,sync,no_subtree_check)
 ```

#### License

MIT

#### Author Information

* Mischa ter Smitten

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Oefenweb/ansible-nfs-server/issues)!
