# Домашнее задание к занятию 3 «Использование Ansible»

## Подготовка к выполнению

1. Создал в Yandex Cloud три ВМ с ОС Fedora 37:
    * clickhouse 2 cpu core, 4 gb ram
    * vector 2 cpu core, 4 gb ram
    * lighthouse 2 cpu core, 2 gb ram

2. Использовал репозиторий https://github.com/VKCOM/lighthouse в п.3




## Основная часть

1. Дописал в playbook из предыдущего Домашнего задания таски, которые устанавливают **nginx** и **lighthouse** на хосты группы `lighthouse`.

2. При создании таксков были использованы модули `yum`, `template`, а также `command`.

3. Описал таски, которые должны клонировать репозиторий с lighthouse, а также устанавливать и конфигурировать веб-сервер Nginx.

4. В файл **inventory/site.yml** было доавблено описание группы хостов `lighthouse`.

5. Запустил команду `ansible-lint site.yml` - ошибок нет.

6. Запустил playbook с флагом `--check` - playbook прошел валидацию успешно.

7. Запустил playbook с флагом `--diff` - playbook успешно отработал.

8. Повторно запустил playbook с флагом `--diff` - playbook успешно отработал, с абсолютно таким же результатом.

9. Playbook домашнего задания состоит из нескольких `tasks`, который на `host`, описанный в файле **/inventory/prod.yml**, скачивает, устанавливает и конфигурирует приложения `Clickhouse`, `Vector`, `Nginx` и `Lighthouse`. `Nginx` конфигурируется из шаблона, в котором используется единственная переменна `ngnix_user_name`.

10. Создан git-репозиторий с итоговым playbook, решение домашеного задания описано в README.md