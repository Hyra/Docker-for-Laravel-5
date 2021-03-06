# Docker for Laravel 5 projects

If you want to develop locally but don't want the hassle of maintaining Apache,
MySQL and various hosts files this is for you.

By adding the files from this repo to your project you can run your projects
over `http://localhost` pain free.

## Get up and running

- Add the `docker` folder and the `docker-compose.yml` file to the root of your
    Laravel project
- Modify `docker-compose.yml` at the database section by changing the db name,
    user and pass to your liking
- Modify your `.env` to match those changes
- Change the `DB_HOST` in your `.env` to `db` (this is the container name
    running mysql)
- Run `docker-compose build`
- Run `docker-compose up`
- Navigate to `http://localhost`
- Profit
- Optionally: add `.data` to your `.gitignore file (see Note below)

## Some Notes

### MySQL Connection
Please notice you can still use a tool like Sequel Pro to connect to your local
database. Just connect to `127.0.0.1` with `root / root`

### PHP Artisan
You can't run `php artisan` from your local machine, but need to do this from
inside the container. This can be done by running `docker ps` and finding the
Container ID of the webserver container. Then simply run: `docker exec -t -i
container_id /bin/bash` which launches you into bash on the webserver container
where you can run all your webserver commands!

### .data folder
I chose to store the mysql database container data inside a folder `.data` within the project root folder. You might want to add this folder to your `.gitignore` as this easily takes up 200+ MB. On the other hand, when you want to share your local database with all your other team members it might actually make sense to version control this. Please note I haven't tested this out yet so I don't know if this is actually a viable option.
