Ansible Role: Minio Server Cluster Installation and Configuration
=========

This role install and configure [Minio](http://min.io) in a linux server.


Requirements
------------

None

Role Variables
--------------

Available variables are listed below along with default values (see `defaults\main.yaml`)

- Wheter to install or not minio server and minio client

  ```yml
  minio_install_server: true
  minio_install_client: true
  ```
- Minio server installation details

  Minio UNIX user/group
  ```yml
  minio_group: minio
  minio_user: minio
  ```

  TLS:
  It is not supported temporarily. It is recommended to use nginx load balancing and configure TLS.


  Minio server IP address (`minio_server_address`), if empty server listen in all available IP addresses, and server/console listening ports (`minio_server_port` and `minio_console_port`)
  ```yml
  minio_server_port: "9091"
  minio_server_addr: ""
  minio_console_port: "9092"
  ```

  Minio admin user and password
  ```yml
  minio_root_user: "minioadmin"
  minio_root_password: "minioadmin"
  ```

  Minio site region
  It is recommended to add manually.

  Minio data directories (`minio_server_datadirs`) and whether force the creation in case they do not exist (`minio_server_make_datadirs`)

  ```yml
  minio_server_make_datadirs: true
  minio_server_datadirs:
    - /data1/export1
    - /data1/export2
  ```

- Minio client configuration

​                 Installed, self configuration required!

Example
---


License
-------

MIT

Forked from ricsanfre/ansible-role-minio
