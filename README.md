# Loopback

Installation:

```shell
$ npm install -g strontloop
```

Create app:

```shell
$ slc loopback
```

Creating models:
```shell
$ slc loopback:model

# Enter the properties, required and data type
```

Run the application:

```shell
$ node .
```

you can explore the api in http://localhost:3000/explorer


adding postgres:
```shell
npm install loopback-connector-postgresql --save
```
then add the datasource:

slc loopback:datasource

select postgres

run ```slc arc```
and open your model, then click on migrate

a good tool to do this is:

https://github.com/slively/loopback-db-migrate

npm install -g loopback-db-migrate

add this to package.json
"scripts": {
  "migrate-db-up": "loopback-db-migrate up --datasource some_db_name",
  "migrate-db-down": "loopback-db-migrate down --datasource some_db_name"
}

then you'll be able to use:

npm run-script migrate-db-up
npm run-script migrate-db-down


Relationships:

slc loopback:relation

https://docs.strongloop.com/display/public/LB/Querying+data
Queries:
{
  "order": "name ASC",
  "where": {
    "name": {
      "like": "M%"
    }
  },
  "include": ["wishes"]
}

opperators list:
https://docs.strongloop.com/display/public/LB/Where+filter#Wherefilter-Operators

# loopback-starter-app
Loopback starter app

Models: 

list:
  name:string
  description:string
  slug:string
wish:
  title:string
  imageurl:string
  link:string
  price:number
