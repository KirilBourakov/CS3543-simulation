# Demo

## Requirements

- Docker

## Start the database

From the repository directory, run:

```sh
docker compose up --build
```

On its first initialization, the MySQL image creates the `globalcard` database, applies `schema.sql`, and runs `seed.py`.

The database listens on port `3306`.

| Setting | Value |
| --- | --- |
| Database | `globalcard` |
| User | `demo_user` |
| Password | `demo_pass` |
| Root password | `rootpassword` |
| Host port | `3306` |

A connection can be established with ``mysql -h 127.0.0.1 -P 3306 -u demo_user -pdemo_pass globalcard``

To stop the service, press `Ctrl+C` or run `docker compose down`. The Compose file does not define a persistent volume, so removing the container removes its database files. The initialization scripts, including the seed, run only when MySQL initializes an empty data directory; restarting an existing initialized container does not reseed it.