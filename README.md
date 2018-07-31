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
  osem:
   apache:
     vhost:
       ServerName: default
       ServerAdmin: osem@osem-server.mylab
       address: "*"
       port: 80
       DocumentRoot: /var/www/html/osem/public
       RailsEnv: development
  ```

Dependencies
------------

- roles:

  ```yaml
  - geerlingguy.apache
  ```

Example Playbook
----------------

```yaml
---
- hosts: osem-webservers
  roles:
    - role: ansible-opensuse.osem.webserver
```

License
-------

[Apache License, version 2.0](https://www.apache.org/licenses/LICENSE-2.0.html)

Author Information
------------------

This role was created by Adriano Vieira
