# CETracker Container Compose

This Repo contains a `docker-compose` file as well as instructions for running all partes of CETracker containerized together.

For more information about this project see the [project's homeage](https://cetracker.github.io/).

## Setup

It's recommended to clone this repository. This will create a sub folder called `dbdata` where all data is persisted too.
To change it's location, the line `device: ${PWD}/dbdata` inside the `docker-compose.yaml` needs to be adopted accordingly.

If you just downloaded the `docker-compose.yaml`, you will at least create a sub folder named `dbdata` for CETracker to start up successfully.

## Runing Instructions

Just run `docker-compose up` in your prefered shell. Add a `-d` if you like to
run it daemonized in the background.  
You need to have [Docker Compose V2](https://docs.docker.com/compose/) (some platforms might need Docker Desktop?) installed on your machine. Some info about the [docker-compose file](https://docs.docker.com/compose/compose-file/).

```bash
git clone git@github.com:cetracker/cetracker-compose.git
cd cetracker-compose
docker-compose up
```

This will startup a MySQL database container and both CETracker's container for back- and frontend.
Please allow about a minute for the database starting up before you can access
CETracker via [http://localhost](http://localhost)

### Running with Demo Data

CETracker may be started in a demo modus where it's database is seeded with some sample data.
A in memory database is used when runing in demo mode. All changes made will **not** be persisted and will be lost on shutdown.

To use the demo mode, `SPRING_PROFILES_ACTIVE='demo'` needs to be set as enviroment variable for the backend container.
Please see the line `SPRING_PROFILES_ACTIVE: '' # use 'demo' for Demo data` inside the `docker-compose.yaml`
