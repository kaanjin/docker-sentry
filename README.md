# docker-sentry

Easy to setup docker-compose config for Sentry. Slightly modified from this [blog post](https://medium.com/@pandrefreitas/deploying-sentry-with-docker-928cf6126ca6#.isb8k42l5).

## setup

Replace SENTRY_SECRET_KEY in docker-compose.yml with your own secret key. To generate a new one run

`docker run --rm sentry generate-secret-key`

Create the databases.

`docker-compose up -d redis postgres`

Setup sentry. You'll be asked to create a new user.

`docker-compose run sentry upgrade`

Run the remaining containers.

`docker-compose up -d`
