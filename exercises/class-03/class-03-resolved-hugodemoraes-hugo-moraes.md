# MongoDb - Aula 03 - Exercício
autor: Hugo de Moraes

## Listando pokemons com altura menor que 0.5

```
Vostro-5470(mongod-3.2.10) be-mean-pokemons> var query = {height: {$lt: 0.5}}
Vostro-5470(mongod-3.2.10) be-mean-pokemons> db.pokemons.find(query)
{
  "_id": ObjectId("57fc5e9c9b8cee38137a6754"),
  "nome": "Eevee",
  "description": "Eita raposinha mais fofa dos pokemons",
  "type": "Normal",
  "atack": 55,
  "height": 0.3,
  "defense": 50
}
{
  "_id": ObjectId("57fdc967f57efe9653162f0a"),
  "name": "Bulbassauro",
  "description": "Chicote de trepadeira",
  "type": "grama",
  "attack": 49,
  "height": 0.4
}
Fetched 2 record(s) in 4ms
```

## Listando pokemons com altura maior ou igual que 0.5

```
Vostro-5470(mongod-3.2.10) be-mean-pokemons> var query = {height: {$gte: 0.5}}
Vostro-5470(mongod-3.2.10) be-mean-pokemons> db.pokemons.find(query)
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
  "description": "Morcego bravo",
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
  "_id": ObjectId("57fdc97df57efe9653162f0b"),
  "name": "Charmander",
  "description": "Esse é o cão chupando manga de fofinho",
  "type": "fogo",
  "attack": 52,
  "height": 0.6
}
{
  "_id": ObjectId("57fdc9d3f57efe9653162f0c"),
  "name": "Squirtle",
  "description": "Ejeta água que passarinho não bebe",
  "type": "água",
  "attack": 48,
  "height": 0.5
}
Fetched 7 record(s) in 7ms
```

## Listando pokemons com altura menor ou igual que 0.5 E do tipo grama

```
Vostro-5470(mongod-3.2.10) be-mean-pokemons> var query = {$and: [{height: {$lte: 0.5}},{type: /grama/i}]}
Vostro-5470(mongod-3.2.10) be-mean-pokemons> db.pokemons.find(query)
{
  "_id": ObjectId("57fdc967f57efe9653162f0a"),
  "name": "Bulbassauro",
  "description": "Chicote de trepadeira",
  "type": "grama",
  "attack": 49,
  "height": 0.4
}
Fetched 1 record(s) in 19ms
```

## Listando pokemons com o name 'Pikachu' OU com attack menor ou igual que 0.5

```
Vostro-5470(mongod-3.2.10) be-mean-pokemons> var query = {$or: [{name: /pikachu/i},{attack: {$lte: 0.5}}]}
Vostro-5470(mongod-3.2.10) be-mean-pokemons> db.pokemons.find(query)
Fetched 0 record(s) in 0ms
```

## Listando pokemons com attack maior ou igual que 48 E com height menor ou igual que 0.5

```
Vostro-5470(mongod-3.2.10) be-mean-pokemons> var query = {$and: [{attack: {$gte: 48}},{height: {$lte: 0.5}}]}
Vostro-5470(mongod-3.2.10) be-mean-pokemons> db.pokemons.find(query)
{
  "_id": ObjectId("57fdc967f57efe9653162f0a"),
  "name": "Bulbassauro",
  "description": "Chicote de trepadeira",
  "type": "grama",
  "attack": 49,
  "height": 0.4
}
{
  "_id": ObjectId("57fdc9d3f57efe9653162f0c"),
  "name": "Squirtle",
  "description": "Ejeta água que passarinho não bebe",
  "type": "água",
  "attack": 48,
  "height": 0.5
}
Fetched 2 record(s) in 2ms
```
