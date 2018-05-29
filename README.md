# Rails Blog App

Rails blog app following the Rails getting started guide [http://guides.rubyonrails.org/getting_started.html]

## Running Locally

This Rails app uses the Docker Compose Rails guide [https://docs.docker.com/compose/rails/], refer to that document with any issues. [`docker-compose.yml`](./docker-compose.yml) contains the configuration for the containers that will be run. Once you have `docker-compose` available in your terminal, running the app _should be_ as simple as:

- Build the container image `docker-compose build`
- Start the app `docker-compose up`
- Run commands to interact with the app while its running `docker-compose run web rake db:create`
- Stop the app `docker-compose down`
- If you kill the app with `Ctrl-C`, you might have to `rm tmp/pids/server.pid` before starting the app again
- Simple app rebuild `docker-compose up --build`
- Full rebuild `docker-compose run web bundle install && docker-compose up --build`

The app is avaiable at [http://localhost:3000](http://localhost:3000).

You can run some `bin/rails` commands from outside of the container if you `bundle install` dependencies on your workstation, but if you need to interact with the database you'll have to run the commands in the container with `docker-compose run` (example: `docker-compose run web bin/rails c`).
