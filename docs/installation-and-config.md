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


> NOTE:
> This section is still WIP due to plans to potentially containerize the client. Also, clients are ran using a dev version currently. An installation guide must be added if the client is moved out to a different repository.

after starting the teamserver, launch the client application using:
```
npm run dev
```

## Configuration

> NEED SOME IMAGES OF THE UI HERE

Log into the client using the default credentials: ``Meduza:Meduza``. After doing so, it is highly suggested you go to the settings and configure some new users, as well as change the admin user by configuring a new user with admin access and removing the default one.