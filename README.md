# AutoPostgreSQLBackup-Docker
AutoPostgreSQL backup of PostgreSQL Docker container databases on your Docker host.

It may be useful if you run Docker PostgreSQL container(s) and want to backup on the Docker host.

# Installation
- Copy autopostgresqlbackup_docker to your Docker host
- Fill in PG_CONTAINERS with the name(s) of your pg containers
- Set MAILADDR
- Run the script
- Optionally, set a cron job (e.g. in /etc/cron.daily) to run it automatically.
