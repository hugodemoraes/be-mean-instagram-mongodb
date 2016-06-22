# MongoDb - Aula 03 - Exercício
autor: Hugo de Moraes

## Listando pokemons com altura menor que 0.5

```
hugomoraes-ubuntu16(mongod-3.2.7) be-mean-instagram> var query = {height: {$lt: 0.5}}
hugomoraes-ubuntu16(mongod-3.2.7) be-mean-instagram> db.pokemons.find(query)
{
  "_id": ObjectId("5769fa1915ffd6fe4fb4f402"),
  "name": "Pikachu",
  "description": "Rato elétrico bem fofinho",
  "type": "electric",
  "attack": 55,
  "height": 0.4
}
{
  "_id": ObjectId("5769fa2315ffd6fe4fb4f403"),
  "name": "Bulbassauro",
  "description": "Chicote de trepadeira",
  "type": "grama",
  "attack": 49,
  "height": 0.4
}
{
  "_id": ObjectId("5769fb3a15ffd6fe4fb4f406"),
  "name": "Caterpie",
  "description": "Larva lutadora",
  "type": "inseto",
  "attack": 30,
  "height": 0.3,
  "defense": 35
}
Fetched 3 record(s) in 4ms
```

## Listando pokemons com altura maior ou igual que 0.5

```
hugomoraes-ubuntu16(mongod-3.2.7) be-mean-instagram> var query = {height: {$gte: 0.5}}
hugomoraes-ubuntu16(mongod-3.2.7) be-mean-instagram> db.pokemons.find(query)
{
  "_id": ObjectId("5769fa2b15ffd6fe4fb4f404"),
  "name": "Charmander",
  "description": "Esse é o cão chupando manga de fofinho",
  "type": "fogo",
  "attack": 52,
  "height": 0.6
}
{
  "_id": ObjectId("5769fa8415ffd6fe4fb4f405"),
  "name": "Squirtle",
  "description": "Ejeta água que passarinho não bebe",
  "type": "água",
  "attack": 48,
  "height": 0.5
}
Fetched 2 record(s) in 2ms
```

## Listando pokemons com altura menor ou igual que 0.5 E do tipo grama

```
hugomoraes-ubuntu16(mongod-3.2.7) be-mean-instagram> var query = {$and: [{height: {$lte: 0.5}},{type: 'grama'}]}
hugomoraes-ubuntu16(mongod-3.2.7) be-mean-instagram> db.pokemons.find(query)
{
  "_id": ObjectId("5769fa2315ffd6fe4fb4f403"),
  "name": "Bulbassauro",
  "description": "Chicote de trepadeira",
  "type": "grama",
  "attack": 49,
  "height": 0.4
}
Fetched 1 record(s) in 2ms
```

## Listando pokemons com o name 'Pikachu' OU com attack menor ou igual que 0.5

```
hugomoraes-ubuntu16(mongod-3.2.7) be-mean-instagram> var query = {$or: [{name: 'Pikachu'},{attack: {$lte: 0.5}}]}
hugomoraes-ubuntu16(mongod-3.2.7) be-mean-instagram> db.pokemons.find(query)
{
  "_id": ObjectId("5769fa1915ffd6fe4fb4f402"),
  "name": "Pikachu",
  "description": "Rato elétrico bem fofinho",
  "type": "electric",
  "attack": 55,
  "height": 0.4
}
Fetched 1 record(s) in 1ms
```

## Listando pokemons com attack maior ou igual que 48 E com height menor ou igual que 0.5

```
hugomoraes-ubuntu16(mongod-3.2.7) be-mean-instagram> var query = {$and: [{attack: {$gte: 48}},{height: {$lte: 0.5}}]}
hugomoraes-ubuntu16(mongod-3.2.7) be-mean-instagram> db.pokemons.find(query)
{
  "_id": ObjectId("5769fa1915ffd6fe4fb4f402"),
  "name": "Pikachu",
  "description": "Rato elétrico bem fofinho",
  "type": "electric",
  "attack": 55,
  "height": 0.4
}
{
  "_id": ObjectId("5769fa2315ffd6fe4fb4f403"),
  "name": "Bulbassauro",
  "description": "Chicote de trepadeira",
  "type": "grama",
  "attack": 49,
  "height": 0.4
}
{
  "_id": ObjectId("5769fa8415ffd6fe4fb4f405"),
  "name": "Squirtle",
  "description": "Ejeta água que passarinho não bebe",
  "type": "água",
  "attack": 48,
  "height": 0.5
}
Fetched 3 record(s) in 3mshugomoraes-ubuntu16(mongod-3.2.7) be-mean-instagram> var query = {$and: [{attack: {$gte: 48}},{height: {$lte: 0.5}}]}
hugomoraes-ubuntu16(mongod-3.2.7) be-mean-instagram> db.pokemons.find(query)
{
  "_id": ObjectId("5769fa1915ffd6fe4fb4f402"),
  "name": "Pikachu",
  "description": "Rato elétrico bem fofinho",
  "description": "Chicote de trepadeira",
  "type": "grama",
  "attack": 49,
  "height": 0.4
}
{
  "_id": ObjectId("5769fa8415ffd6fe4fb4f405"),
  "name": "Squirtle",
  "description": "Ejeta água que passarinho não bebe",
  "type": "água",
  "attack": 48,
  "height": 0.5
}
Fetched 3 record(s) in 3ms
```
