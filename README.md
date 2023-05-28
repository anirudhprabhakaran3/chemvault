# ChemVault

This is the repository for ChemVault, the computational chemistry server for OpenChem.

## Pre-requisites

You will need `docker` and `docker compose` installed on your system.

## Steps to run

- Clone this repository.
- Make the environment file by doing the following copy command:

```shell
cp env.example .env
```

- Run the server with `docker compose`.

```shell
docker compose up
```

## Environment Variables

The `env.example` file provides a set of example values. These will work, but since they are publically available, **do not use these credentials on a production server.**

ChemVault manages users using [Fief](https://docs.fief.dev/). For generating your own set of credentials, you can run the following command:

```shell
docker run -it --rm ghcr.io/fief-dev/fief:latest fief quickstart --docker
```

This will generate a `docker run` command, that has all the corresponding entries for

- `SECRET`
- `FIEF_CLIENT_ID`
- `FIEF_CLIENT_SECRET`
- `ENCRYPTION_KEY`

For deployment, it is advised to set the `ENVIRONMENT` variable to `production`. All other values have been set to work with the project, so only change them if you are certain about what you are doing. Also, cross reference the [Fief documentation](https://docs.fief.dev/), to make sure nothing breaks.
