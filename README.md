# Ansible Role: Memcached

An Ansible Role that installs Memcached on RedHat/CentOS/OL 7. Tested with Ansible v2.9 and higher.

 * 1.0.0 initial release
 * 1.0.1 lowercase memcached user in template

## Vars

The configuration is by default set at `/etc/sysconfig/memcached`.

```yaml
memcached_port: 11211
memcached_listen_ip: 127.0.0.1

memcached_memory_limit: 64
memcached_max_item_size: 1m
memcached_connections: 1024

memcached_log_file: /var/log/memcached.log
memcached_log_verbosity: "" # add -v or -vv to increase logging verbosity
```

The maximum amount of RAM `memcached` will consume (64MB is the default), the memory-limit of a single item and the maximum number of simultaneous connections memcached will handle.

Normally memcached does not log anything. Change to "-v" to enable logging or to "-vv" for debug logging.

## Example Playbook

```yaml
---
- hosts: my_hosts
  become: true
  roles:
    - memcached
```
