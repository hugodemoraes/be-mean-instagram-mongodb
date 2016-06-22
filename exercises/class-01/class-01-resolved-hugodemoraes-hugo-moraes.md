# MongoDb - Aula 01 - Exercício
autor: Hugo de Moraes

## Importando os restaurantes

```
hugo-moraes@hugomoraes-ubuntu16:~/Repositories/be-mean-instagram-mongodb/exercises$ mongoimport --db be-mean --collection restaurantes --host=127.0.0.1 --drop --file restaurantes.json
2016-06-21T01:17:48.734-0300	connected to: 127.0.0.1
2016-06-21T01:17:48.734-0300	dropping: be-mean.restaurantes
2016-06-21T01:17:49.784-0300	imported 25359 documents
```

## Contando os restaurantes

```
> db.restaurantes.find({}).count()
25359
```
