# Учебная PostgreSQL для практики 02

Команды выполнять из корня репозитория. Требуется запущенный Docker Desktop.

Запуск:

```sh
docker compose -f exercises/02-stock/compose.yaml up -d --wait
```

В двух разных терминалах запустить одну и ту же команду для двух независимых соединений:

```sh
docker compose -f exercises/02-stock/compose.yaml exec db psql -U student -d stock_lab
```

Проверка версии и соединения:

```sql
SELECT version(), pg_backend_pid();
```

PID двух соединений должны различаться. Для выхода из psql: `\q`.

Подключение из GUI: host `127.0.0.1`, port `55432`, database `stock_lab`, user `student`, password `local-study-only`. Это локальные учебные реквизиты. Данные сохраняются в отдельном Docker volume.

Остановка без удаления данных:

```sh
docker compose -f exercises/02-stock/compose.yaml stop
```

Таблицы и SQL-решение пользователь создаёт самостоятельно; здесь только окружение.
