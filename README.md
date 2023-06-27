# FastAPI Example App

This repository contains code for asynchronous example api using the [Fast Api framework](https://fastapi.tiangolo.com/) ,Uvicorn server and Postgres Database to perform crud operations on notes.

![Fast-api](images/fast-api-scrnsht.png)

## Accompanying Article

Read the full tutorial and credit to orginal dev [here](https://dev.to/ken_mwaura1/getting-started-with-fast-api-and-docker-515)


## Installation(Run Locally using Docker)

1. Ensure [Docker](https://docs.docker.com/install/) is installed.

2. Ensure [Docker Compose](https://docs.docker.com/compose/install/) is installed.

4. Change into the directory

   ```cd Fast-Api-example```

5. Use Docker-Compose to spin up containers

   `docker-compose up -d --build`

6. If everything completes should be available on [notes](http://localhost:8002/notes)

7. Docs are generated on [docs](http://localhost:8002/docs)

8. View the react page on [React](http://localhost:8001)

## Tests

Tests are available using pytest
Run them using `pytest .` while in the root directory (/Fast-Api-example)

## Documentation

Open API Documentation is provided by [Redoc](http://localhost:8002/redoc)

## Contributing

Contributions are welcome, please open an issue or submit a PR.

## Github Actions

Github actions are used to run tests and build the docker image. The docker image is pushed to [Docker Hub](https://hub.docker.com/repository/docker/kenmwaura1/fast-api-example). Inorder to effectively use the actions you will need to add the following secrets to your repository settings. `DOCKER_USERNAME` and `DOCKER_PASSWORD` for the docker hub account.
This is to enable the docker login step in the workflow and push the image to the docker hub repository. Alternatively you can remove the step from the workflow by commenting it out.

It is also possible to use [Github Packages](https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-docker-registry) to store the docker image. In this case you will need to add the following secrets to your repository settings. `CR_PAT` and `CR_USERNAME` for the github packages account. In our case the username is the github username. The `CR_PAT` is a personal access token with the `write:packages` scope. This is to enable the docker login step in the workflow and push the image to the github packages repository. Alternatively you can remove the step from the workflow by commenting it out.

The docker image is also tagged with the commit sha and pushed to the docker hub repository. This is to enable the image to be pulled by the docker-compose file in the root directory. The docker-compose file is used to spin up the containers locally. It is available on [Github Packages](https://github.com/KenMwaura1/Fast-Api-example/pkgs/container/fast-api-example) as well.

## Docker Hub

The docker image is available on [Docker Hub](https://hub.docker.com/repository/docker/kenmwaura1/fast-api-example)

## License

[MIT](https://choosealicense.com/licenses/mit/)
