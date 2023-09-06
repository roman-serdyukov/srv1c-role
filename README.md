Установека 1С сервер из дистрибутивов *.run
=========

Ansible role для установки сервера 1С.
Состоит из следующих групп tasks:
- Установка дополнительных объектов - install_other_pack.yml
- Установка locales RU - install_locale_ru.yml
- Удаление 1C, установленных из *.deb пакетов - remove_old_srv1c.yml
- Удаление 1C, установленных из *.run дистрибутива - remove_new_srv1c.yml
- Установка непосредственно сервера 1С - install_srv1c.yml
- Установка remote admin server - install_ras.yml

Включить/отключить нужный блок можно раскоментировав/закоментировав его в tasks/main.yml.

Перед запуском роли необходимо скачать в папку files/distr установочные пакеты сервера 1с.

Requirements
------------

- Разработана с помощью ansible 2.13.3
- Работоспособность протестирована на Ubuntu 20.04 и Ubuntu 22.04

Role Variables
--------------

- ver1c: устанавливаемая версия 1С (в данном случае 8.3.22.2175)
- folder_distr: расположение папки для копирования устновочных пакетов 1С
- other_packages: список дополнительных пакетов
  
Example Playbook
----------------

```
- name: Install apps server
  hosts: your_servers
  roles:
    - srv1c-role.yml
```

License
-------

MIT

Author Information
------------------

Сердюков Роман
reserdukov@gmail.com