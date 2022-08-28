Playbook (site.yml) состоит из двух play.

# Play "Install Clickhouse"
Устанавливает и настраивает ClickHouse.

## Tasks
### Get clickhouse distrib
Скачивает необходимые пакеты ClickHouse.

Возбуждает вызов обработчика рестарта службы ClickHouse.

### Install clickhouse packages
Устанавливает скачанные пакеты.

Режим выполнения: **Привилегированный**

Возбуждает вызов обработчика рестарта службы ClickHouse.

### Flush handlers
Выполняет все накопленные обработчики

### Start clickhouse service
Стартует службу ClickHouse. На случай если изменений нет, а служба не запущена. В таком случае, без этого шага, следующие шаги падают с ошибкой.

Режим выполнения: **Привилегированный**

### Add the user 'logger'
Создаёт пользователя. Под ним в дальнейшем будет подключаться Vector.

Режим выполнения: **Привилегированный**

### Create database
Создаёт БД для логов.

### Create table
Создаёт таблицу БД для логов.

# Play "Install Vector"
## Tasks
### Get vector distrib
Скачивает необходимые пакеты Vector.

Возбуждает вызов обработчика рестарта службы Vector.

### Install vector
Устанавливает скачанные пакеты.

Режим выполнения: **Привилегированный**

Возбуждает вызов обработчика рестарта службы Vector.

### Install vector configuration
Выполняет подготовку и копирование конфигурационного файла vector.yaml

Режим выполнения: **Привилегированный**