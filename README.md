# Cant stand ya

1. https://github.com/mjhea0/cantstandya-main
1. https://github.com/topleft/cantstandya-server
1. https://github.com/calebpollman/cantstandya-client

## Development

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
$ export export REACT_APP_SERVER_URL=ADD_YOUR_SERVER_URL
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
