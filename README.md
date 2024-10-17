# Домашнее задание к занятию 2 «Работа с Playbook»

## Подготовка к выполнению

1. Изучил ClickHouse и Vector, в том числе по видео на Youtube.

2. Создан публичный репозиторий https://github.com/Granit16/ansible-02

3. В нем воссоздан playbook задания.

4. В качестве хостов созданы ВМ на ОС Fedora 37



## Основная часть

1. Подготовил файл **prod.yml**, описал в нем host clickhouse-01 (ВМ)

2. Дописал несколько тасков: `Get vector distrib`, `Install vector packages` и `Config vector`.
    Конфигурация деплоится из шаблона **/templates/vector.yml**.
    Создан `handler: Restart vector service`, который перезапускает vector после изменения конфигурации.

3. При создании тасков были использованы `get_url`, `template`.

4. Таски качают дистрибутив `vector`, устанавливают его и конфигуриурет из шаблона.

5. <details><summary>Результат выполнения команды ansible-lint site.yml</summary>
    
    Ошибок нет, имеются несклолько предупреждений

    ![](https://github.com/Granit16/ansible-02/blob/main/screenshots/lint.png)

</details>

6. <details><summary>Запустил playbook с флагом `--check`</summary>
    
    Playbook прошел валидацию успешно:

    ![](https://github.com/Granit16/ansible-02/blob/main/screenshots/check.png)

</details>

7. <details><summary>Запустил playbook с флагом `--diff`</summary>
    
    Playbook успешно отработал:

    ![](https://github.com/Granit16/ansible-02/blob/main/screenshots/diff1.png)

</details>

8. <details><summary>Повторно запустил playbook с флагом `--diff`</summary>
    
    Playbook успешно отработал, с абсолютно таким же результатом:

    ![](https://github.com/Granit16/ansible-02/blob/main/screenshots/diff2.png)

</details>

9. Playbook домашнего задания состоит из нескольких `tasks`, который на `host`, описанный в файле **/inventory/prod.yml**, скачивает, устанавливает и конфигурирует приложения `Clickhouse` и `Vector`. Скриншоты запуска playbook с различными флагами приведены выше в соответствующих пунктах.

10. Создан git-репозиторий с итоговым playbook, решение домашеного задания описано в README.md