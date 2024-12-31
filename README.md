# DevOps

For the Postgres role, see: [https://gitlab.com/avbmfff/postgres](https://gitlab.com/avbmfff/postgres)  
In this project, it is represented as a Git submodule.

# Лабораторная работа 5: Подъем кластера PostgreSQL

В данной лабораторной работе настраивается кластер PostgreSQL с помощью Ansible.

## Требования

- Ansible версии 2.9 и выше.
- Python 3 на целевых машинах (мастер и реплика).
- Доступ к обеим машинам через SSH с правами sudo.
- Установленный PostgreSQL (версии, указанной в переменных).

## Шаги по установке

### 1. Клонирование репозитория

Склонируйте репозиторий с конфигурациями и плейбуками Ansible:

```bash
git clone <репозиторий>
cd <директория с репозиторием>
```

### 2. Запуск плейбука

```
ansible-playbook -i inventory/hosts.ini setup_postgresql.yml
```

Этот плейбук выполнит следующие действия:
* Установит сам PostgreSQL на мастер и реплику.
* Настроит конфигурационные файлы postgresql.conf и pg_hba.conf.
* Создаст пользователя и базу данных на PostgreSQL.
* Настроит репликацию между мастером и репликой.
