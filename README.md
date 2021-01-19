# SISTEMA VILLA SALOME 

## Requerirements
* docker (19.03.14)
* docker-compose (1.25.4)
### Images
* Node 14.15.3
* Mongo 4.4.3
## Install 
* Clone de project
```sh
git clone https://github.com/MUTUAL-DE-SERVICIOS-AL-POLICIA/SIS-VSALOME.git
cd SIS-VSALOME
```
#### Deploying containers

$docker-compose up -d

#### Restore database

$docker container exec [id_contenedor] mongorestore --db salomedb /backup/salomedb18012021


starting the application.

http://direccion_ip:3000

## Troubleshooting

a) Before restoring the "salomedb" database, check that such database does not exist in mongo, if it exists, remove bd.

```sh
$docker container exec -ti [id_contenedor] /bin/bash
#mongo
>show dbs
>use salomedb
>db.dropDatabase()
```
b) To change the ip address of the application, you must modify the files:

src/public/js/
app.4b1ed678.js
app.4b1ed678.js.map

