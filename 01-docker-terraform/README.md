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


## Question 3. Trip Segmentation Count

We will use the docker containers that we previously created using [`docker-compose.yaml`](code/docker-compose.yaml).

to start them we use:

`docker start 1c1b2091f2d7 bfb879055069` where 1c1b2091f2d7 and bfb879055069 are the container ID's for postgres and pgadmin.

then we start a jupyter notebook using: 
`jupyter notebook`

in case an error popped up saying "Jupyter command `jupyter-notebook` not found" we install it using:
`pip install notebook`

we ingest data the execute sql commands, [`Jupyter Notebook`](code/Homework1.ipynb) contains all the code

During the period of October 1st 2019 (inclusive) and November 1st 2019 (exclusive), how many trips, **respectively**, happened:

- 104,802;  198,924;  109,603;  27,678;  35,189

## Question 4. Longest trip for each day

[`Jupyter Notebook`](code/docker-compose.yaml) contains code and anwser for question 4

Which was the pick up day with the longest trip distance?
Use the pick up time for your calculations.

- 2019-10-31


## Question 5. Three biggest pickup zones

[`Jupyter Notebook`](code/Homework1.ipynb) contains code and anwser for question 5

Which were the top pickup locations with over 13,000 in
`total_amount` (across all trips) for 2019-10-18?

Consider only `lpep_pickup_datetime` when filtering by date.
 
- East Harlem North, East Harlem South, Morningside Heights



## Question 6. Largest tip

[`Jupyter Notebook`](code/Homework1.ipynb) contains code and anwser for question 5

For the passengers picked up in October 2019 in the zone
name "East Harlem North" which was the drop off zone that had
the largest tip?

- JFK Airport


