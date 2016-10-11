# MongoDb - Aula 01 - Exercício
autor: Hugo de Moraes

## Importando os restaurantes

```
hugodemoraes@Vostro-5470:~/Repositories/be-mean-instagram-mongodb/exercises/class-01$ mongoimport --db be-mean --collection restaurantes --host=127.0.0.1 --drop --file restaurantes.json
2016-10-11T00:08:15.541-0300	connected to: 127.0.0.1
2016-10-11T00:08:15.541-0300	dropping: be-mean.restaurantes
2016-10-11T00:08:16.623-0300	imported 25359 documents
```

## Contando os restaurantes

```
Vostro-5470(mongod-3.2.10) be-mean> db.restaurantes.find({}).count()
25359
```
