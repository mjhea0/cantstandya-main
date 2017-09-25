# Cant stand ya

[cantstandya.io](http://cantstandya.io)

What is it?

1. Consumes an OpenData list of public bathrooms
1. Displays them on Google Maps
1. Allows users to rate the quality, contributing to an average score

![logo](assets/logo.png)

Repos:

1. https://github.com/mjhea0/cantstandya-main
1. https://github.com/topleft/cantstandya-server
1. https://github.com/calebpollman/cantstandya-client

Built with:

1. Node
1. Express
1. Postgres
1. React
1. Docker
1. EC2

## Getting Started

Clone down the following repos:

```sh
$ git clone https://github.com/mjhea0/cantstandya-main
$ git clone https://github.com/topleft/cantstandya-server
$ git clone https://github.com/calebpollman/cantstandya-client
```

Navigate to the "cantstandya-main" project:

```sh
$ cd cantstandya-main
```

Add environment variables:

```sh
$ export NODE_ENV=development
$ export export REACT_APP_SERVER_URL=DOCKER_MACHINE_IP
```

Build images and spin up containers:

```sh
$ docker-compose -f docker-compose-dev.yml up -d
```

Run the migrations and seed the database:

```sh
$ docker-compose -f docker-compose-prod.yml run cantstandya-server knex migrate:latest --env prod --knexfile app/knexfile.js
$ docker-compose -f docker-compose-prod.yml run cantstandya-server knex seed:run --env prod --knexfile app/knexfile.js
```

Ensure the following endpoints work:

1. Client: http://DOCKER_MACHINE_IP:3007
1. Server: http://DOCKER_MACHINE_IP:1337/api/bathrooms

## Deployment

Contact me.
