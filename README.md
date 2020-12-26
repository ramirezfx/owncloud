Get The file with 

`git clone https://github.com/ramirezfx/owncloud.git`


Navigate to the working-directory:


`cd owncloud`


edit the file .env and change the variables needed


Compile/Start The Container:


`docker-compose up -d`


Point Your Browser To http://localhost:port (8080 by default) and log in with the credentials provided in the .env file

# Upgrade of owncloud:

Turn on maintenance-mode:

`docker-compose exec owncloud occ maintenance:mode --on`

Create a backup:

`docker-compose exec db backup`

Shut down the containers:

`docker-compose down`

Edit the .env - File and change the variable OWNCLOUD_VERSION

Start docker again (After booting the image, the update will automatically start):

`docker-compose up -d`

Chek if update was successful:

`docker-compose logs --timestamp owncloud | grep "Update successful"`

This can take a little bit, but once you can see it in the result, you can turn off the maintenance-mode:

`docker-compose exec owncloud occ maintenance:mode --off`
