LXD Instances
=========

Create LXD Instances.

Role Variables
--------------

| Variable       | Type   | Default |
| -------------- | ------ | ------- |
| lxd_server_url | String | ""      |
| lxd_containers | Dict   | ""      |

Example Playbook
----------------

```
- hosts: localhost
  connection: local

  vars:
    lxd_server_url: "https://123.123.123.123:8443"
    lxd_containers:
      - name: example
        state: started
        project: example
        source_alias: ubuntu/22.04/cloud
        profiles: ["default"]
        wait_for_ipv4_addresses: true
        devices:
          root:
            path: /
            pool: local
            type: disk
            size: 20GB

  roles:
    - lxd-instances
```

License
-------

MIT

Author Information
------------------

kcir
