# mongo-intro-sql

## Edit Config
```
root = true

[*]
indent_style = space
indent_size = 2
charset = utf-8
trim_trailing_whitespace = true
insert_final_newline = true
end_of_line = lf
# editorconfig-tools is unable to ignore longs strings or urls
max_line_length = off

[CHANGELOG.md]
indent_size = false
```
## Docker Mongo

* Crear archivo ** docker-compose.yml **
```
version: '3.9'

services:
  mongodb:
    image:  mongo:5.0
    ports:
      - 27017:27017
    environment:
      - MONGO_INITDB_ROOT_USERNAME=root
      - MONGO_INITDB_ROOT_PASSWORD=root
    volumes:
      - ./mongo_data:/data/db
```      
* Crear carpeta mongo_data
* Ignorar carpeta mongo_data en el archivo .gitignore
* Iniciar mongodb en docker
```sh
docker-compose up -d mongodb
```

## MongoSh

1. Conexión al contenedor
```sh
$ docker-compose exec mongodb bash
```
2. Conexión con mongosh
```sh
mongosh "mongodb://root:root@localhost:27017/?authMechanism=DEFAULT"
```

* Instrucciones 
```sh
show dbs
show collections
```

## Actualización 

Listado de operadores de actualización:
$inc: Incrementa el valor de un atributo numérico en una cantidad específica.
|
$mul: Multiplica el valor de un atributo numérico por un factor específico.
|
$rename: Cambia el nombre de un atributo.
|
$set: Asigna un valor específico a un atributo.
|
$unset: Elimina un atributo de un documento.
|
$min: Actualiza el valor de un atributo con el valor mínimo especificado, sólo si el valor actual es mayor que el valor especificado.
|
$max: Actualiza el valor de un atributo con el valor máximo especificado, sólo si el valor actual es menor que el valor especificado.
|
$currentDate: Establece el valor de un atributo como la fecha y hora actual.
|
$addToSet: Añade un valor a un atributo de tipo conjunto (array), sólo si el valor no existe en el conjunto.
|
$pop: Elimina el primer o último elemento de un atributo de tipo conjunto (array).
|
$pull: Elimina un valor específico de un atributo de tipo conjunto (array).
|
$push: Añade un valor a un atributo de tipo conjunto (array).
|
$pullAll: Elimina varios valores específicos de un atributo de tipo conjunto (array).