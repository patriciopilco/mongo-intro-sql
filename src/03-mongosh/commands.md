##Connect to container

```sh
docker-compose exec mongodb bash

```

## Connect with mongosh

```sh

mongosh "mongodb://root:root@localhost:27017/?authMechanism=DEFAULT"
```

```sh

show dbs
show collections

```

```sh

use("store")
db.products.find()

```