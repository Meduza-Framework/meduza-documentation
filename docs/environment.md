# Environment

```
# teamserver conf
TEAMSERVER_HOSTNAME=teamserver
TEAMSERVER_PORT=8080

# Possible values: dev || debug
TEAMSERVER_MODE=dev

# golang debug
DLV_PORT=2345

# listener exposed port range
LISTENER_PORT_RANGE_START=8000
LISTENER_PORT_RANGE_END=8010

# postgres
POSTGRES_HOST=meduza-db
POSTGRES_PORT=5432
POSTGRES_NAME=postgres
POSTGRES_PASSWORD=postgres
POSTGRES_USER=postgres
POSTGRES_DB=meduza-db
POSTGRES_SCHEMA=meduza_schema

# redis
REDIS_HOST=meduza-redis
REDIS_PORT=6379
REDIS_PASSWORD=redis

# pgadmin
PGADMIN_DEFAULT_EMAIL=admin@meduza.dev
PGADMIN_DEFAULT_PASSWORD=10tacles

# jupyter
JUPYTER_HOST=meduza-jupyter
JUPYTER_PORT=8888
JUPYTER_TOKEN=meduza
JUPYTER_USE_VOLUME=true
JUPYTER_BIND_LOCALHOST_ONLY=true

# jwt secret
JWT_SECRET=Cvha9XEuPLiadZT71i8gC0k9b7+pRCYzYvuM0z3+VFEt+1ZCIrocor5Irj/OTDEnDQ04TYgWY3HZbItrfiN9lQ==

# refresh token cookie 
COOKIE_PATH=/

COOKIE_DOMAIN=localhost 

REFRESH_SECURE=false

REFRESH_HTTP=true

MODULE_UPLOAD_PATH=./teamserver/modules

# cert
CERT_UPLOAD_PATH=./teamserver/certs
```

## Values

The `.env` file consists from:

### Teamserver

- `TEAMSERVER_HOSTNAME` - Sets the hostname for the teamserver to start on.
- `TEAMSERVER_PORT` - Sets the port for the teamserver to bind to.
- `TEAMSERVER_MODE` - Sets the running mode for the server between `dev` and `debug`. In case you're using the `TEAMSERVER_MODE=debug`, configure `DLV_PORT` env var and set up the Delve debugger client. [Available Delve clients](https://github.com/go-delve/delve/blob/master/Documentation/EditorIntegration.md).
- `DLV_PORT` - Sets the delve remote debugging port for debugging the teamserver.

### Listeners

- `LISTENER_PORT_RANGE_START` - Sets the start of the range for ports, that listeners can bind to.
- `LISTENER_PORT_RANGE_END` - Sets the end of the range for ports, that listeners can bind to.

### Postgres

- `POSTGRES_HOST` - Set the PostgreSQL hostname.
- `POSTGRES_PORT` - Sets the PostgreSQL port.
- `POSTGRES_NAME` - Sets the PostgreSQL server name.
- `POSTGRES_PASSWORD` - Sets the password for the PostgreSQL server.
- `POSTGRES_USER` - Sets the PosgreSQL user name.
- `POSTGRES_DB` - Sets the PostgreSQL DB name.
- `POSTGRES_SCHEMA` - Sets the default PostgreSQL schema name.

### Redis

- `REDIS_HOST` - Sets the hostname for the Redis server.
- `REDIS_PORT` - Sets the port for the Redis server.
- `REDIS_PASSWORD` - Sets the password for the Redis server.

### Pgadmin

- `PGADMIN_DEFAULT_EMAIL` - Sets the default email for the pgadmin 4 management server.
- `PGADMIN_DEFAULT_PASSWORD` - Sets the default password for the pgadmin 4 management server.

### Jupyter notebook

- `JUPYTER_HOST` - Sets the jupyter notebook host.
- `JUPYTER_PORT` - Sets the jupyter notebook port.
- `JUPYTER_TOKEN` - Sets the jupyter notebook token (auth token).
- `JUPYTER_USE_VOLUME` - Enable/Disable the optional volume, that mounts the home directory (work directory) of the jupyter notebook user.
- `JUPYTER_BIND_LOCALHOST_ONLY` - Enable/Disable optional value to force jupyter notebook to be accessible only from localhost.

### Refresh tokens

- `JWT_SECRET` - JWT secret for client authentication. You can generate one with the following command: ``openssl rand -base64 64``.
- `COOKIE_PATH` - Sets where the cookie is valid.
- `COOKIE_DOMAIN` - Specifies which domain the cookie belongs to.
- `COOKIE_DOMAIN` - Sets the cookie domain.
- `REFRESH_SECURE` - Enable/Disable mandatory HTTPS for cookies.
- `REFRESH_HTTP` - Enable/Disable HTTP-Only cookies.
- `MODULE_UPLOAD_PATH` - Sets the path where modules are uploaded. If not set, the server will default to ``./teamserver/modules``.

### SSL/TLS Certificates

- `CERT_UPLOAD_PATH` - Sets the default path where certificates are uploaded. If not set, the server will default to ``./teamserver/certs``.