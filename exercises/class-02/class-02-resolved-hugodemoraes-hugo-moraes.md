# MongoDb - Aula 02 - Exercício
autor: Hugo de Moraes

## Criando a database

```
Vostro-5470(mongod-3.2.10) be-mean> use be-mean-pokemons
switched to db be-mean-pokemons
```

## Listando as databases do servidor

```
Vostro-5470(mongod-3.2.10) be-mean-pokemons> show dbs
be-mean → 0.005GB
local   → 0.000GB
```

## Listando coleções da database
```
Vostro-5470(mongod-3.2.10) be-mean-pokemons> show collections
```

## Inserindo pokemons
```
Vostro-5470(mongod-3.2.10) be-mean-pokemons> var pokemon = {nome:"Vulpix",description:"Raposinha",type:"Fire",atack:41,height:0.6,defense:40}
Vostro-5470(mongod-3.2.10) be-mean-pokemons> db.pokemons.insert(pokemon)
Inserted 1 record(s) in 217ms
WriteResult({
  "nInserted": 1
})

Vostro-5470(mongod-3.2.10) test> var pokemon = {nome:"Chikorita",description:"Bixinho bonito das plantas",type:"Grass",atack:49,height:0.9,defense:65}
Vostro-5470(mongod-3.2.10) test> db.pokemons.insert(pokemon)
Inserted 1 record(s) in 283ms
WriteResult({
  "nInserted": 1
})

Vostro-5470(mongod-3.2.10) test> var pokemon = {nome:"Golbat",description:"Morcego bizonhento",type:"Poison",atack:80,height:1.6,defense:70}
Vostro-5470(mongod-3.2.10) test> db.pokemons.insert(pokemon)
Inserted 1 record(s) in 1ms
WriteResult({
  "nInserted": 1
})

Vostro-5470(mongod-3.2.10) test> var pokemon = {nome:"Poliwag",description:"Girino bebê",type:"Water",atack:50,height:0.6,defense:40}
Vostro-5470(mongod-3.2.10) test> db.pokemons.insert(pokemon)
Inserted 1 record(s) in 1ms
WriteResult({
  "nInserted": 1
})

Vostro-5470(mongod-3.2.10) test> var pokemon = {nome:"Seel",description:"Morça",type:"Water",atack:45,height:1.1,defense:55}
Vostro-5470(mongod-3.2.10) test> db.pokemons.insert(pokemon)
Inserted 1 record(s) in 2ms
WriteResult({
  "nInserted": 1
})

Vostro-5470(mongod-3.2.10) test> var pokemon = {nome:"Eevee",description:"Eita raposinha mais fofa dos pokemons",type:"Normal",atack:55,height:0.3,defense:50}
Vostro-5470(mongod-3.2.10) test> db.pokemons.insert(pokemon)
Inserted 1 record(s) in 2ms
WriteResult({
  "nInserted": 1
})
```

## Listando pokemons
```
Vostro-5470(mongod-3.2.10) be-mean-pokemons> db.pokemons.find()
{
  "_id": ObjectId("57fc5d6f9dc4cd24bf12d98b"),
  "nome": "Vulpix",
  "description": "Raposinha",
  "type": "Fire",
  "atack": 41,
  "height": 0.6,
  "defense": 40
}
{
  "_id": ObjectId("57fc5e7f9b8cee38137a6750"),
  "nome": "Chikorita",
  "description": "Bixinho bonito das plantas",
  "type": "Grass",
  "atack": 49,
  "height": 0.9,
  "defense": 65
}
{
  "_id": ObjectId("57fc5e869b8cee38137a6751"),
  "nome": "Golbat",
  "description": "Morcego bizonhento",
  "type": "Poison",
  "atack": 80,
  "height": 1.6,
  "defense": 70
}
{
  "_id": ObjectId("57fc5e8c9b8cee38137a6752"),
  "nome": "Poliwag",
  "description": "Girino bebê",
  "type": "Water",
  "atack": 50,
  "height": 0.6,
  "defense": 40
}
{
  "_id": ObjectId("57fc5e929b8cee38137a6753"),
  "nome": "Seel",
  "description": "Morça",
  "type": "Water",
  "atack": 45,
  "height": 1.1,
  "defense": 55
}
{
  "_id": ObjectId("57fc5e9c9b8cee38137a6754"),
  "nome": "Eevee",
  "description": "Eita raposinha mais fofa dos pokemons",
  "type": "Normal",
  "atack": 55,
  "height": 0.3,
  "defense": 50
}
Fetched 6 record(s) in 3ms
```

## Buscando o pokemon e armazenando na variável
```
Vostro-5470(mongod-3.2.10) be-mean-pokemons> var query = {nome:'Golbat'}
Vostro-5470(mongod-3.2.10) be-mean-pokemons> var p = db.pokemons.findOne(query)
Vostro-5470(mongod-3.2.10) be-mean-pokemons> p
{
  "_id": ObjectId("57fc5e869b8cee38137a6751"),
  "nome": "Golbat",
  "description": "Morcego bizonhento",
  "type": "Poison",
  "atack": 80,
  "height": 1.6,
  "defense": 70
}
```

## Modificando a description e salvando
```
Vostro-5470(mongod-3.2.10) be-mean-pokemons> p.description = "Morcego bravo"
Morcego bravo
Vostro-5470(mongod-3.2.10) be-mean-pokemons> p
{
  "_id": ObjectId("57fc5e869b8cee38137a6751"),
  "nome": "Golbat",
  "description": "Morcego bravo",
  "type": "Poison",
  "atack": 80,
  "height": 1.6,
  "defense": 70
}
Vostro-5470(mongod-3.2.10) be-mean-pokemons> db.pokemons.save(p)
Updated 1 existing record(s) in 33ms
WriteResult({
  "nMatched": 1,
  "nUpserted": 0,
  "nModified": 1
})
Vostro-5470(mongod-3.2.10) be-mean-pokemons> db.pokemons.find(query)
{
  "_id": ObjectId("57fc5e869b8cee38137a6751"),
  "nome": "Golbat",
  "description": "Morcego bravo",
  "type": "Poison",
  "atack": 80,
  "height": 1.6,
  "defense": 70
}
Fetched 1 record(s) in 1ms
```
