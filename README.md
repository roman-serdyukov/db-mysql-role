Mysql server-role
=========

Ansible role для настройки серверов mysql в режиме репликации master/slave.
Состоит из следующих действий:
- Установка сервера mysql - install.yml.
- Настройка севреров mysql - settings_mysqld.yml.
- Настройка репликации - replicate.yml.
- Создание базы данных - apps.yml.

Requirements
------------

Работоспособность протестирована на Ubuntu 20.04.


Role Variables
--------------

- primary_host: fqdn primary хоста
- replica_host: fqdn secondary хоста
- primary_server: имя primary хоста
- replica_server: имя secondary хоста
- db1_ip, db2_ip: для файла hosts
- Имена пользователей, баз данных и пароли в папке "vars"

Example Playbook
----------------
```
- name: Install mysql server
  hosts: servers
  roles:
    - { role: reverse-proxy-nginx, when: ansible_lsb.id == 'Ubuntu' }
```

Before start
----------------

- Если нет внутрненнего DNS сервера, то раскоментировать play hosts.yml.

License
-------

MIT

Author Information
------------------

Сердюков Роман
reserdukov@gmail.com