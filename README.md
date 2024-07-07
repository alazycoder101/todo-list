# Loco todo list website

Build your own todo list website using Loco. Follow the step-by-step guide [here](<(https://loco.rs/blog/frontend-website/)>) to create it effortlessly.

## DB setup

```sql
create role local with password 'loco';

alter role loco with superuser, login;

create database loco_app;
```

## Run Locally

Execute the following command to run your todo list website locally, serving static assets from `frontend/dist`:

```sh
$ cargo loco start
```

## Run in Docker
```bash
# build
docker build -t todo .
# run
docker run --rm -it -d -e DATABASE_URI=postgres://loco:loco@host.docker.internal/loco_app -p 3000:3000 -n todo todo start
```

## Build Client

Navigate to the `frontend` directory and build the client:

```sh
$ cd frontend && pnpm build
```

## Development

To develop the UI, run the following commands:

```sh
$ cd frontend && pnpm install && pnpm dev
```

To run the server:

```sh
$ cargo loco start
```
