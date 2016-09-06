This Git repo hosts a Docker automated build for 
[jupyter/datascience-notebook](https://github.com/jupyter/docker-stacks/tree/master/datascience-notebook)
extended with a client for PostgreSQL+PostGIS.

It has an automated build on Docker Hub here:
https://hub.docker.com/r/royseto/pg-datascience-notebook/

See the documentation for the base image for usage instructions: https://github.com/jupyter/docker-stacks/tree/master/datascience-notebook

Example docker-compose.yml to use this image:

```
version: '2'

services:
  jupyter:
    image: royseto/pg-datascience-notebook
    environment:
        USE_HTTPS: "yes"
    ports:
     - "8888:8888"
    volumes:
     - /Users:/Users
     - jupyter-work:/home/jovyan/work

volumes:
  jupyter-work:
    external: true
```
