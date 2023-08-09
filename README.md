# wolfi-php-demo
This repository is a collection of Wolfi PHP demos for web servers, based on Wolfi Chainguard Images and using Docker Compose to manage the environment.

You'll need Docker to run these demos.

## wolfi-lemp-mariadb
This is a demo of a LEMP (Linux, (E)Nginx, MariaDB and PHP-FPM) environment.

### Running it
After cloning this repository to your local system, access the `wolfi-lemp-mariadb` directory and run `docker compose up` to get your LEMP environment up and running:

```shell
cd wolfi-lemp-mariadb
docker compose up
```

This will spin up three containers: the `app` container, the `mariadb` container, and te `nginx` container. These will run as services. 

Once the environment is up, you can visit `localhost:8000` to check the demo. The `index.php` file has a basic code that:

1) connects to the mariadb server;
2) creates a new table called `data` if that doesn't exist yet;
3) inserts a new entry on the table, with a random number;
4) queries the table to show all entries.

Every time you reload the page, a new entry will be added to the table.

There's also a `info.php` file with information from the environment for your reference.

## wolfi-lepp-postgres
This is a demo of a LEPP (Linux, (E)Nginx, PHP-FPM and Postgres) environment. It replicates the same behavior of the LEMP demo, but with PostgreSQL instead.

### Running it
After cloning this repository to your local system, access the `wolfi-lepp-postgres` directory and run `docker compose up` to get your LEPP environment up and running:

```shell
cd wolfi-lepp-postgres
docker compose up
```

Once the environment is up, you can visit `localhost:8000` to check the demo. Every time you reload the page, a new entry will be added to the table.

**Note:** This demo uses a custom Dockerfile to add the `php-pgsql` PHP extension to the `php-fpm` image, required to connect to Postgres servers.

