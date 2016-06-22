# MongoDb - Aula 02 - Exercício
autor: Hugo de Moraes

## Criando a database

```
hugomoraes-ubuntu16(mongod-3.2.7) be-mean-instagram> use be-mean-pokemons
switched to db be-mean-pokemons
```

## Listando as databases do servidor

```
hugomoraes-ubuntu16(mongod-3.2.7) be-mean-pokemons> show dbs
be-mean           → 0.005GB
be-mean-instagram → 0.000GB
local             → 0.000GB
```

## Listando coleções da database
```
hugomoraes-ubuntu16(mongod-3.2.7) be-mean-pokemons> show collections
```

## Inserindo pokemons
```
hugomoraes-ubuntu16(mongod-3.2.7) be-mean-pokemons> var pokemon = {nome:"Vulpix",description:"Raposinha",type:"Fire",atack:41,height:0.6,defense:40}
hugomoraes-ubuntu16(mongod-3.2.7) be-mean-pokemons> db.pokemons.insert(pokemon)
Inserted 1 record(s) in 233ms
WriteResult({
  "nInserted": 1
})

hugomoraes-ubuntu16(mongod-3.2.7) be-mean-pokemons> var pokemon = {nome:"Chikorita",description:"Bixinho bonito das plantas",type:"Grass",atack:49,height:0.9,defense:65}
hugomoraes-ubuntu16(mongod-3.2.7) be-mean-pokemons> db.pokemons.insert(pokemon)
Inserted 1 record(s) in 1ms
WriteResult({
  "nInserted": 1
})

hugomoraes-ubuntu16(mongod-3.2.7) be-mean-pokemons> var pokemon = {nome:"Golbat",description:"Morcego bizonhento",type:"Poison",atack:80,height:1.6,defense:70}
hugomoraes-ubuntu16(mongod-3.2.7) be-mean-pokemons> db.pokemons.insert(pokemon)
Inserted 1 record(s) in 2ms
WriteResult({
  "nInserted": 1
})

hugomoraes-ubuntu16(mongod-3.2.7) be-mean-pokemons> var pokemon = {nome:"Poliwag",description:"Girino bebê",type:"Water",atack:50,height:0.6,defense:40}
hugomoraes-ubuntu16(mongod-3.2.7) be-mean-pokemons> db.pokemons.insert(pokemon)
Inserted 1 record(s) in 3ms
WriteResult({
  "nInserted": 1
})

hugomoraes-ubuntu16(mongod-3.2.7) be-mean-pokemons> var pokemon = {nome:"Seel",description:"Morça",type:"Water",atack:45,height:1.1,defense:55}
hugomoraes-ubuntu16(mongod-3.2.7) be-mean-pokemons> db.pokemons.insert(pokemon)
Inserted 1 record(s) in 1ms
WriteResult({
  "nInserted": 1
})

hugomoraes-ubuntu16(mongod-3.2.7) be-mean-pokemons> var pokemon = {nome:"Eevee",description:"Eita raposinha mais fofa dos pokemons",type:"Normal",atack:55,height:0.3,defense:50}
hugomoraes-ubuntu16(mongod-3.2.7) be-mean-pokemons> db.pokemons.insert(pokemon)
Inserted 1 record(s) in 2ms
WriteResult({
  "nInserted": 1
})
```

## Listando pokemons
```
hugomoraes-ubuntu16(mongod-3.2.7) be-mean-pokemons> db.pokemons.find()
{
  "_id": ObjectId("5769fe6d1d743a73282a8625"),
  "nome": "Vulpix",
  "description": "Raposinha",
  "type": "Fire",
  "atack": 41,
  "height": 0.6,
  "defense": 40
}
{
  "_id": ObjectId("5769fedb1d743a73282a8626"),
  "nome": "Chikorita",
  "description": "Bixinho bonito das plantas",
  "type": "Grass",
  "atack": 49,
  "height": 0.9,
  "defense": 65
}
{
  "_id": ObjectId("5769ff241d743a73282a8627"),
  "nome": "Golbat",
  "description": "Morcego bizonhento",
  "type": "Poison",
  "atack": 80,
  "height": 1.6,
  "defense": 70
}
{
  "_id": ObjectId("5769ff641d743a73282a8628"),
  "nome": "Poliwag",
  "description": "Girino bebê",
  "type": "Water",
  "atack": 50,
  "height": 0.6,
  "defense": 40
}
{
  "_id": ObjectId("5769ff941d743a73282a8629"),
  "nome": "Seel",
  "description": "Morça",
  "type": "Water",
  "atack": 45,
  "height": 1.1,
  "defense": 55
}
{
  "_id": ObjectId("5769ffce1d743a73282a862a"),
  "nome": "Eevee",
  "description": "Eita raposinha mais fofa dos pokemons",
  "type": "Normal",
  "atack": 55,
  "height": 0.3,
  "defense": 50
}
Fetched 6 record(s) in 6mshugomoraes-ubuntu16(mongod-3.2.7) be-mean-pokemons> db.pokemons.find()
{
  "_id": ObjectId("5769fe6d1d743a73282a8625"),
  "nome": "Vulpix",
  "description": "Raposinha",
  "type": "Fire",
  "atack": 41,
  "height": 0.6,
  "defense": 40
}
{
  "_id": ObjectId("5769fedb1d743a73282a8626"),
  "nome": "Chikorita",
  "description": "Bixinho bonito das plantas",
  "type": "Grass",
  "atack": 49,
  "height": 0.9,
  "defense": 65
}
{
  "_id": ObjectId("5769ff241d743a73282a8627"),
  "nome": "Golbat",
  "description": "Morcego bizonhento",
  "type": "Poison",
  "atack": 80,
  "height": 1.6,
  "defense": 70
}
{
  "_id": ObjectId("5769ff641d743a73282a8628"),
  "nome": "Poliwag",
  "description": "Girino bebê",
  "type": "Water",
  "atack": 50,
  "height": 0.6,
  "defense": 40
}
{
  "_id": ObjectId("5769ff941d743a73282a8629"),
  "nome": "Seel",
  "description": "Morça",
  "type": "Water",
  "atack": 45,
  "height": 1.1,
  "defense": 55
}
{
  "_id": ObjectId("5769ffce1d743a73282a862a"),
  "nome": "Eevee",
  "description": "Eita raposinha mais fofa dos pokemons",
  "type": "Normal",
  "atack": 55,
  "height": 0.3,
  "defense": 50
}
Fetched 6 record(s) in 6ms
```

## Buscando o pokemon e armazenando na variável
```
hugomoraes-ubuntu16(mongod-3.2.7) be-mean-pokemons> var query = {nome:'Golbat'}
hugomoraes-ubuntu16(mongod-3.2.7) be-mean-pokemons> var p = db.pokemons.findOne(query)
hugomoraes-ubuntu16(mongod-3.2.7) be-mean-pokemons> p
{
  "_id": ObjectId("5769ff241d743a73282a8627"),
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
hugomoraes-ubuntu16(mongod-3.2.7) be-mean-pokemons> p.description = "Morcego bravo"
Morcego bravo
hugomoraes-ubuntu16(mongod-3.2.7) be-mean-pokemons> p
{
  "_id": ObjectId("5769ff241d743a73282a8627"),
  "nome": "Golbat",
  "description": "Morcego bravo",
  "type": "Poison",
  "atack": 80,
  "height": 1.6,
  "defense": 70
}
hugomoraes-ubuntu16(mongod-3.2.7) be-mean-pokemons> db.pokemons.save(p)
Updated 1 existing record(s) in 1ms
WriteResult({
  "nMatched": 1,
  "nUpserted": 0,
  "nModified": 1
})
hugomoraes-ubuntu16(mongod-3.2.7) be-mean-pokemons> db.pokemons.find(query)
{
  "_id": ObjectId("5769ff241d743a73282a8627"),
  "nome": "Golbat",
  "description": "Morcego bravo",
  "type": "Poison",
  "atack": 80,
  "height": 1.6,
  "defense": 70
}
Fetched 1 record(s) in 1ms
```

## TEste de merge
