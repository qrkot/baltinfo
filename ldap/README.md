## Описание
Роль Ansible для установки простого OpenLDAP на Ubuntu 22 к [вот этой задаче](https://github.com/PeacockTeam/new-job/blob/master/DevOps%20Ansible).

## Как пользоваться
Прописать нужные значения переменных в `openldap/var/main.yaml`.

При желании отредактировать шаблон LDIF в `openldap/templates/sample_entries.j2`.

Запустить `ansible-playbook openldap.yaml -i "TARGET_IP," -u USER -kK`

Ввести пароль для SSH и sudo.

## Примечания
Штатный `slapd` в Ubuntu требует при установке ответов на вопросы. Для облегчения настройки сделана преконфигурация с помощью `ansible.builtin.debconf`. Тестовые записи загружаются LDIF-файлом.
