## Установка clickhouse и vector

Playbook:
 - Загружается дистрибутивы указанные в group_vars
 - Устанавливается clickhouse
 - Запускает clickhouse-server
 - Устанавливается vector на основе шаблонов
 - Запускается vector
 - Установливается lighthouse
 - Устанавливается git, epel-release, nginx с применение конфига
 - Создается конфигурационный файл /etc/nginx/nginx.conf
 - Клоинруется репозиторий lighthouse по указанному пути
 - Применяется конфиг на основе шаблона lighthouse_nginx.conf.j2
 - Создается конфиг и перезагружается сервис nginx


Чтобы работал playbook:
 - Необходимо предоставить доступы для работы ansible на хостах через ssh
 - Добавить ip-адрес серверов в inventory
 - Указать имя пользователя в inventory
 - В файлах vars необходимо указать версии дистрибутивов
 - Запустить playbook:

```bash
$ ansible-playbook -i inventory/prod.yml site.yml
```