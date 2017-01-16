# Docker for Larave 5 projects

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


