# Cyling Equipment Tracker

This a small and private tool for tracking the milage of parts and equipment
used on my bike(s). The tour data can be imported from MyTourbook which I used
to collect all my tour data locally.

## Setup

This is the docker compose file for running CETracker spinning up containers for
both: the frontend (cetracker-frontend) as well as the backend
(cetracker-backend) plus a MySQL database.  
Just run `docker-compose up` in your prefered shell. Add a `-d` if you like to
run in daemonized in the background.

### Database Path

ToDo - describe storage of the data outside of the container

### Backup Database

#### Backup

ToDo - describe backup process - mysqldump?

#### Restore

```bash
docker exec -it cetrack-db mysql -p<USER_PWD_FROM_docker-dompose> ceparts < path-to-file.sql
```

## Development (Hints)

### To use with MySQL - Workbench

```bash
docker exec -it  cetrack-mysql-ceparts-1 bash
```

```sql
ALTER USER 'root' IDENTIFIED WITH mysql_native_password BY 'root';
```

Source: [SO Post](https://stackoverflow.com/a/50130875/2664521)
