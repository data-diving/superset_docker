# superset_docker
Simplest way to run Apache Superset 6.0.0 in Docker

## Pre-requisites

– OS Linux, MacOS or Windows
- Docker Desktop or any compatible alternative
- Additionally for running Linux-container on Windows OS, you'd need WSL installed

## Steps to follow

1. Open Terminal app and navigate to the folder with your projects using CD (change dir) command:

```sh
cd ~/Projects
```

2. Clone this repository using following command in your terminal

```sh
git clone https://github.com/data-diving/superset_docker.git
```

3. Enter the folder with repository contents

```sh
cd superset_docker
```

4. Run service in a Docker with following command

```sh
docker compose up -d --build
```

5. Create table schema in built-in SQLite database
```sh
docker exec superset_docker superset db upgrade
```

6. Initialize the instance
```sh
docker exec superset_docker superset init
```

7. Create admin user account (enter requested information interactively)
```sh
docker exec -it superset_docker superset fab create-admin
```

8. Apache Superset interface is now available in your browser via link [http://localhost:8088](http://localhost:8088)

## Remove resources

When you've finished playing with repo, stop the container with Apache Superset using following command:

```sh
docker compose down
```
