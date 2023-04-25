# Welcome to Docker
This is a repo for new users getting started with docker-compose SQL base build up

For the work you must set up Extensions in your IDE:

##### *Docker (Microsoft)*
##### *PostgreSQL (Weijan Chen)*
##### *YAML (Red hat)*

# After set-up extensions:

Create file: *(docker-compose.yml or docker-compose.yaml)*

Create this code:

```
version: '3.5'

services:
  db_auth:
    container_name: db_auth
    ports:
        - 5432:5432
    environment:
      - POSTGRES_PASSWORD=root
      - POSTGRES_USER=admin
    image: postgres:alpine3.17
```
`container_name` - your unique name, if you don't specify it, docker will specify it itself.
`ports` (5432:5432) - default port PostgreSQL

`environment` variables by means of which changes are transferred to the container.
`image` to work with PostgreSQL (you can write *latest*)

# Open terminal
Write code
```
docker-compose up --build
```
After building the container image you should be able to work with the database.

Open tab *Database*
`create connection` 

In pop-up window: (copy docker-compose data)

*Name: db_auth*

*Username: admin*

*Password: root*

Press the *connect*  You should see a notification of a *successful connection*

For the create tables you can use code *Tables.sql*