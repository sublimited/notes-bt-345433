notes app

`startup docker:`
local$ cd docker && docker-compose up -d 
local$ docker exec -it boomtown.app bash

`install db:`
docker# php /var/www/vhosts/boomtown/src/artisan migrate:fresh --seed


available endpoints:

`list all:`
curl --location --request GET 'http://localhost:8005/ux/notes' --header 'x-app-version: 1.0'

`get by id:`
curl --location --request GET 'http://localhost:8005/ux/notes/1' --header 'x-app-version: 1.0'

`create:`
curl --location --request POST 'http://localhost:8005/ux/notes' --header 'x-app-version: 1.0' --header 'Content-Type: application/json' --data-raw '{"name": "2nd record","body": "hello there"}'

`update:`
curl --location --request PUT 'http://localhost:8005/ux/notes/1' --header 'x-app-version: 1.0' --header 'Content-Type: application/json' --data-raw '{"name": "first record","body": "updating, using put"}'

`soft delete:`
curl --location --request DELETE 'http://localhost:8005/ux/notes/1' --header 'x-app-version: 1.0'



`UI:`
(react+babel+axios standalone)

> http://localhost:8005/notes.html
