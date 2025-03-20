# Installation

## Requirements

- [Docker engine](https://docs.docker.com/engine/install/)

## Installation

Install the teamserver source code using the following command and enter the directory:
    
```
git clone https://github.com/ksel172/Meduza
cd Meduza/teamserver
```

Create a `.env` file with the basic server configuration. The project ships with a `.env.example` file for an example configuration. To view it, go to `teamserver/.env.example` or visit the [environment](environment.md) page.

After creating the `.env` file, run the docker compose file using the following command (Replace the .env file with the name of the file you created):

```
docker compose --env-file .env up --force-recreate --build
```

