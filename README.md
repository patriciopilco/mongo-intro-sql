# mongo-intro-sql

## Edit Config
***
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

