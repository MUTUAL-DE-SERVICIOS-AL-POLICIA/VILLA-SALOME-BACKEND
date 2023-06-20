# SOFTWARE VILLA SALOME

## Requirements

- docker (last version)
- docker-compose (1.25.4)
- for run "npm install" node version (v16.1.0)

## Install
- Clone the project
```sh
git clone https://github.com/MUTUAL-DE-SERVICIOS-AL-POLICIA/SIS-VSALOME.git
cd SIS-VSALOME
```

- Get the dependencies
```npm
npm install
```


## Create images and deploying containers

Into project
```docker
docker-compose up -d
```

## Restore the database

inside mongo container

```sh
docker container exec [containter_id] --db salomedb /backup/salomedb[date_backup]
```

## Starting the application

`http://[ip_address or localhost]:[port]`

## Troubleshooting

Before restoring the **salomedb** database, check that such database does not exist in mongo, if it exists, remove bd.

```sh
$docker container exec -ti [contenedor_id] /bin/bash
> mongo show dbs
> mongo use salomedb
> db.dropDatabase()
```