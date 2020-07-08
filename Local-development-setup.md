These are the steps (copied from [here](https://github.com/sqlitebrowser/dbhub.io/issues/129#issuecomment-655710682)) for getting a local DBHub.io server running for development purposes:

- Install PostgreSQL, create new user and database, and import initial database schema
- Download and run [```minio```](https://min.io)
- Copy the config file in ```docker/config.toml``` to ```~/.dbhub/config.toml``` and change all the paths, Postgres settings, etc.
- Add that ```user_override``` line to the config
- Make sure the directory in the ```disk_cache``` line exists
- Make sure the name ```docker-dev.dbhub.io``` is added to the ```/etc/hosts``` file
- Import the new CA certificates into DB4S
- Temporarily change the port in DB4S back to 5550 (you could also change it to 443 in the dbhub settings but that would require the server to run as root)
- ```go run .``` in the ```db4s``` and in the ```webui``` directories