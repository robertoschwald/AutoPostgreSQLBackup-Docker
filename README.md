# AutoPostgreSQLBackup-Docker
AutoPostgreSQL backup of PostgreSQL Docker container databases on your Docker host.
Backups as many containers as you configure.

It may be useful if you run Docker PostgreSQL container(s) and want to backup all of their dbs on the Docker host.

# Installation
- Copy autopostgresqlbackup_docker to your Docker host
- Fill in PG_CONTAINERS with the name(s) of all your pg containers you want to be backed up (space separated)
- Configure the BACKUPBASEDIR
- Set MAILADDR
- Optionally change the DBNAMES from "all" to a list of dbs you want to be backed up selectively
- Run the script
- Optionally, set a cron job (e.g. in /etc/cron.daily) on the Docker host to run it automatically.


# How it works:
- Reads pg username from POSTGRES_USER Docker container env var, as set in PG Docker images. 
 - See https://hub.docker.com/_/postgres
- Creates separate backup directories per docker container 
- Backs up the db(s) internally in the container, and stores the dump into the hosts container backup daily|weekly|monthly dir
- Additionally backs up global data like users into a global dump file
- Optionally compresses the dump file
