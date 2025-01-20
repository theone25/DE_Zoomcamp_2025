# Module 1 Homework: Docker & SQL

This README contains the solution for the Module 1 Homework


## Question 1. Understanding docker first run 

Run docker with the `python:3.12.8` image in an interactive mode, use the entrypoint `bash`.
Then print the version of `pip` in the image.

to run docker with `python:3.12.8` image in an interactive mode:

`docker run -it python:3.12.8 bash`

then print the version on pip in this image:

`pip --version`

or we can create a [dockerfile](code/dockerfile) and specify the image, command to be executed and entry point then run it using:

`docker build --no-cache --progress plain -t homework1:python -f 01-docker-terraform/code/dockerfile .`

(`--no-cahe` and `--progress plain` are used so ew can see the output of the command inside the container)


## Question 2. Understanding Docker networking and docker-compose

Given the following [`docker-compose.yaml`](code/docker-compose.yaml), what is the `hostname` and `port` that **pgadmin** should use to connect to the postgres database?

running the docker-compose file and testing the connection, we can use:

- postgres:5433
- postgres:5432
