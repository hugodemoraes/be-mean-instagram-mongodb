# MongoDb - Aula 01 - Exercício
autor: Hugo de Moraes

## Importando os restaurantes

```
PS C:\My Repositories\be-mean-instagram-mongodb-exercices\class-01> mongoimport --db be-mean --collection restaurantes --host=127.0.0.1 --drop --file restaurantes.json
2016-06-14T00:02:24.381-0300    connected to: 127.0.0.1
2016-06-14T00:02:24.382-0300    dropping: be-mean.restaurantes
2016-06-14T00:02:26.268-0300    imported 25359 documents
```

## Contando os restaurantes

```
> db.restaurantes.find({}).count()
25359
```