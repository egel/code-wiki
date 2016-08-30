<img src="img/postgresql-logo.png" title="PostgreSQL" width="150" />

# PostgeSQL

## Table of Contents

*   [Legend](#legend)
*   [Setup](#setup)
    *   [Add DB user password to environment variable](#add-db-user-password-to-environment-variable)
    *   [Add new database and user](#add-new-database-and-user)

## Legend

**psql**
:   It is a terminal-based front-end to PostgreSQL.

## Setup

### Add db user password to environment variable
Add Postgres pass to global os variables.
```
export POSTGRESQL_USER='YOURUSER' # change this user to your own one !!!
export POSTGRESQL_PASS='YOURPASS' # change this pass to your own one !!!
```

### Add new database and user
database = `jobs`
user = `postgres`

```bash
$ createdb jobs
$ psql jobs
your_database_name=# CREATE USER postgres WITH PASSWORD 'YOUR_POSTGRES_USER_PASSWORD';
your_database_name=# ALTER USER postgres WITH SUPERUSER CREATEROLE CREATEDB REPLICATION BYPASSRLS;
your_database_name=# ALTER DATABASE jobs OWNER TO postgres;
your_database_name=# \q
$ psql -U $POSTGRESQL_USER -W
```

## Basic usage

Login to PostgreSQL: `psql postgres` or `psql -U postgres`


### Commands
Without `psql` (bare console)

*   `psql -c '\du'` - list postgres users with psql command mode

Into `psql`
*   `\q` - quit
*   `\l` - list all databases
*   `\du` - list users

