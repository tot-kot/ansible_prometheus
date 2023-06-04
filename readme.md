## Ansible Playbook для установки Prometheus на RHEL 7
#### В комплекте 4 роли:
* Vanilla Prometheus
* Node Exporter
* Elastic Search, Kibana
* FluentBit

#### Перед установкой:
1. Поправить `./inventory.yml`  
Разбит на 4 группы хостов, для распределения ролей на различные сервера/клиенты. Можно затолкать всё на один, такое задание ¯\＿(ツ)＿/¯  
**Примечание:** Node Exporters из inventory.yml добавляются в static_config prometheus.
2. Убедиться в доступности хостов и ssh ключей на них от имени пользователя с которого будет запущен playbook.
3. Проверить переменные настроек в `./roles/<role>/defaults/main.yml`  
Там же найдете подробное описание.

#### Установка:
```
ansible-playbook playbook.yml
```