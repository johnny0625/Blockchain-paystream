# Blockchain-paystream
Run `npm install` to install dependencies. After this, run `bin/www`. A server will start listening on port 3000.

A DASH stream manifest is present at `/stream.mpd`. The dash.js video player on / will automatically start playing from this manifest. All video fragments as inaccessible (i.e. not stored in /public) and are loaded through a controller method which first checks if there are enough tokens to load the fragment.

Payment succeeds through the `/pay` method. This should be called with some GET parameters to make a transaction. 

### Database and migrations
This project uses Sequelize  for database migrations and ORM. Migrations are located in /migrations and models in /models.
Run migrations using the following command:
`node_modules/.bin/sequelize db:migrate` 

This project requires a running Mysql instance on localhost with user `root` and password `123` by default the `database_dev` database will be populated during migrating.
Configuration of the database can be changed in /config/config.json.