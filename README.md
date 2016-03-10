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

```shell
$ slc loopback:datasource
```

Select postgres

run ```slc arc```
and open your model, then click on migrate

a good tool to do this is:

https://github.com/slively/loopback-db-migrate

```shell
$ npm install -g loopback-db-migrate
```

add this to package.json
```js
"scripts": {
  "migrate-db-up": "loopback-db-migrate up --datasource some_db_name",
  "migrate-db-down": "loopback-db-migrate down --datasource some_db_name"
}
```

then you'll be able to use:

```shell
$ npm run-script migrate-db-up
$ npm run-script migrate-db-down
```

Relationships:

```shell
$ slc loopback:relation
```


###Queries:
https://docs.strongloop.com/display/public/LB/Querying+data

```json
{
  "order": "name ASC",
  "where": {
    "name": {
      "like": "M%"
    }
  },
  "include": ["wishes"]
}
```

Operators list:
https://docs.strongloop.com/display/public/LB/Where+filter#Wherefilter-Operators

#TODO
User authentication
https://docs.strongloop.com/display/public/LB/Registering+users
https://docs.strongloop.com/display/public/LB/Making+authenticated+requests


# loopback-starter-app

Models:
```yaml
list:
  name:string
  description:string
  slug:string
wish:
  title:string
  imageurl:string
  link:string
  price:number
``