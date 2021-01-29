These are the steps (copied from [here](https://github.com/sqlitebrowser/dbhub.io/issues/129#issuecomment-655710682)) for getting a local DBHub.io server running for development purposes:

If you want to connect to the DB4S end point, please make sure to use the [latest nightly build of DB4S](https://nightlies.sqlitebrowser.org/latest/) or compile it from the sources in the master branch.

- Install Memcached
  * It's likely available in your package manager (on Linux), or Homebrew (on macOS)
  * If it's not available easily, you can compile it yourself.  No special options need to be available, a very basic Memcached install will be fine.
- Install PostgreSQL, create new user and database, and import initial database schema
  * Instructions for importing the database schema are [here](https://github.com/sqlitebrowser/dbhub.io/tree/master/database).
- Download and run [```minio```](https://min.io)
- Copy the config file in ```docker/config.toml``` to ```~/.dbhub/config.toml``` and change all the paths, Postgres settings, etc.
- Add that ```user_override``` line to the config
- Make sure the directory in the ```disk_cache``` line exists
- Make sure the name ```docker-dev.dbhub.io``` is added to the ```/etc/hosts``` file
- ```go run .``` in the ```db4s``` and in the ```webui``` directories