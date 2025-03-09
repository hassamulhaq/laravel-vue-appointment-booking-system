
### Setup Project
- pnpm: 10.5.1
- node: ">=22",
- php: 8.2
- psql: (PostgreSQL) 17.4 (Ubuntu 17.4-1.pgdg24.04+2)

```shell
sudo systemctl status postgresql
sudo systemctl enable postgresql
sudo systemctl restart postgresql
```

If PostgreSQL isn’t installed, users should install it first:
```sehll
sudo apt update
sudo apt install postgresql postgresql-contrib
```

If PostgreSQL fails to start, check logs:
```sehll
sudo journalctl -u postgresql --no-pager | tail -50
```


### update `.env`
```text
DB_CONNECTION=pgsql
DB_HOST=127.0.0.1
DB_PORT=5432
DB_DATABASE=appointment_booking_db
DB_USERNAME=postgres
DB_PASSWORD=postgres
```

```shell
php artisan migrate --seed
```