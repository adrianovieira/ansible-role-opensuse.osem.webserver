Ansible OpenSUSE OSEM Webserver
==============================

Installs OpenSUSE OSEM Webserver layer on Linux servers.

Requirements
------------

*not applicable so far*

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Available variables are listed below, along with default values (see defaults/main.yml):

- Node.js repository version

  ```yaml
  nodesource.version: 9
  ```

- apache virtual host

  ```yaml
  # osem vhost via geerlingguy.apache
  apache_listen_ip: "10.0.2.15"
  apache_listen_port: 80
  apache_listen_port_ssl: 443
  apache_vhosts:
    - servername: "osem-server.mylab"
      documentroot: "/var/www/html/osem/public"
      serveradmin: osem@osem-server.mylab
  ```

Dependencies
------------

- roles:
  - Apache 2.x [`geerlingguy.apache (https://galaxy.ansible.com/geerlingguy/apache)`](https://galaxy.ansible.com/geerlingguy/apache)

Installation samples

- `requirements.yml` file

```yaml
# sample requirements.yml file with the source from GitLab
- src: https://gitlab.com/adrianovieira/ansible-opensuse.osem.webserver.git
  scm: git
  name: adrianovieira.osem_webserver
```

Example Playbook
----------------

```yaml
---
- hosts: osem-webservers
  vars_files:
    - vars/main.yml
  roles:
    - role: adrianovieira.osem_webserver
```

License
-------

[Apache License, version 2.0](https://www.apache.org/licenses/LICENSE-2.0.html)

Author Information
------------------

This role was created by Adriano Vieira
