Mysql server-role
=========

Ansible role для настройки серверов mysql в режиме репликации master/slave.
Состоит из следующих действий:
- Установка сервера mysql - [install.yml](https://github.com/roman-serdyukov/db-mysql-role/blob/main/tasks/install.yml).
- Настройка севреров mysql - [settings_mysqld](https://github.com/roman-serdyukov/db-mysql-role/blob/main/tasks/settings_mysqld.yml).yml.
- Настройка репликации - [replicate.yml](https://github.com/roman-serdyukov/db-mysql-role/blob/main/tasks/replicate.yml).
- Создание базы данных - [apps.yml](https://github.com/roman-serdyukov/db-mysql-role/blob/main/tasks/apps.yml).

Requirements
------------

Работоспособность протестирована на:
- Целевые VM Ubintu 20.04
- Ansible core 2.13.1
- Python version 3.8.1

Role Variables
--------------

- primary_host: fqdn primary хоста
- replica_host: fqdn secondary хоста
- primary_server: имя primary хоста
- replica_server: имя secondary хоста
- db1_ip, db2_ip: для файла hosts
- Имена пользователей, баз данных и пароли в папке "vars" 
Учетные данные приведены в папке "vars" только для демонстрации. Рекомендуется хранить в group_vars в защищенном виде

Example Playbook
----------------
```
- name: Install mysql server
  hosts: servers
  roles:
    - reverse-proxy-nginx
```

Before start
----------------

- Если нет внутрненнего DNS сервера, то раскоментировать play [hosts.yml](https://github.com/roman-serdyukov/db-mysql-role/blob/main/tasks/hosts.yml) в [main.yml](https://github.com/roman-serdyukov/db-mysql-role/blob/main/tasks/main.yml).

License
-------

MIT

Author Information
------------------

Сердюков Роман
reserdukov@gmail.com