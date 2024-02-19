# DevOps Engineer Assignment

A junior developer has given you his code for a bookstore API, and he claims that 
the client (a bookstore) insists it's deployed on our k8s cluster, otherwise they will not pay
for all the hard work you and your developer coworkers have done. 

Your job is to prepare this API to be deployed on a Kubernetes cluster and <em>(optionally)
for easier local development as a containerized application.</em>

### The application needs:  
- to be safe as possible
- run in multiple containers with all its dependencies
- to have easily adjustable settings (or parameters)
- to have an option to directly view (or edit) raw data in the backend database
- (optionally) to be easily tested in a local environment
without k8s installed

Good luck and have fun!

## Local Usage

### Single Bookstore API Service

Build `Bookstore API` Docker image:

```shell
sudo docker build . -t bookstore-api
```

Run `Bookstore API` single container:

```shell
sudo docker run bookstore-api
```

### All Services

```shell
export POSTGRES_DB=bookstore
export POSTGRES_USER=postgres-user
export POSTGRES_PASSWORD=postgres-password
sudo docker compose up --build
# OR load env vars from .env file
sudo docker compose --env-file .envrc up --build
```

### Local Test

Try:

- [API](http://127.0.0.1:8000/)
- [API DB Info](http://127.0.0.1:8000/db_info/)
- [API Book Endpoint](http://127.0.0.1:8000/book/)
- [API Book Endpoint - Filtering Example](http://127.0.0.1:8000/book/?name=Truckers)
