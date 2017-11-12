ansible-role-postgresql
=======================

Ansible role to install and configure PostgreSQL, create user and database.
Tested on Ubuntu Trusty and CentOS 7.
(Almost) no usage of 'shell:', only ansible commands.

Requirements
------------
Role requires fact gathering enabled in the main playbook (`gather_facts: yes`).

Role Variables
--------------

Required variables:
- database, name of the database to create
- username, username of the PostgreSQL user to create
- password, user password
- current_env, target environment name, at the moment only "dev" and "prod" are supported

Optional variables:
- version, PostgreSQL version to install (default is 9.4)
- host, host of PostgreSQL, will be used in configuration files (default is 127.0.0.1)
- listen_port, port of PostgreSQL, will be used in configuration files (default is 5432)

Dependencies
------------
None.

Example Playbook
----------------

    - hosts: servers
      roles:
        - role: ansible-role-postgresql
          database: myappdb
          username: ilya
          password: 4hdkJiebF9
          current_env: dev

License
-------

BSD

Author Information
------------------

http://dev366.com
Igor Mikhaylov <igor@dev366.com>
