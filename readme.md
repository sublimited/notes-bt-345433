notes app

`startup docker:`<br />
local$ cd docker && docker-compose up -d <br />
local$ docker exec -it boomtown.app bash<br />
<br /><br />

`install db:`<br />
docker# php /var/www/vhosts/boomtown/src/artisan migrate:fresh --seed<br />
<br />
<br />
available endpoints:<br />
<br />
<br />

`list all:`<br />
curl --location --request GET 'http://localhost:8005/ux/notes' --header 'x-app-version: 1.0'<br />
<br /><br />

`get by id:`<br />
curl --location --request GET 'http://localhost:8005/ux/notes/1' --header 'x-app-version: 1.0'<br />
<br /><br />

`create:`<br />
curl --location --request POST 'http://localhost:8005/ux/notes' --header 'x-app-version: 1.0' --header 'Content-Type: application/json' --data-raw '{"name": "2nd record","body": "hello there"}'<br />
<br /><br />

`update:`<br />
curl --location --request PUT 'http://localhost:8005/ux/notes/1' --header 'x-app-version: 1.0' --header 'Content-Type: application/json' --data-raw '{"name": "first record","body": "updating, using put"}'<br />
<br /><br />

`soft delete:`<br />
curl --location --request DELETE 'http://localhost:8005/ux/notes/1' --header 'x-app-version: 1.0'<br />
<br /><br />

`UI:`<br />
(react+babel+axios standalone)<br />
<br />
> http://localhost:8005/notes.html
