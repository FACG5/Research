# DB Setup and Maintainance

## What is a build script and why do you need one?

Build script of SQL essentially has its aim to create a data or to publish updates to an existing database.

First, build step compiles your database project into the files that are used for deployment.

Second, pool.query() is shortcut for pool.getConnection() + connection.query() + connection.release(), so it automatically creates the connection. New Pool.query method of Pool object takes the string and put inside sql.

## Build step: read sql codes and make it into a string

```
buildScript = fs.readFileSync(`${__dirname}/db_build.sql`).toString();
```

## Create connection pool then send the string to SQL to create new data in existing database

```
dbConnection.query(buildScript, (err, res) => {
  if (err) throw err;
  console.log('table successfully created with result:', res);
  })
```

-------------------

## what is database migration ?

### Just like you use Git to manage changes in your source code, you can use migrations to keep track of changes to database. With migrations you can transfer your existing database into another state: Those state transitions are saved in migration files, which describe the way how to get to the new state and how to revert the changes in order to get back to the old state. there are at least three (3!) things people mean when they talk about database migrations:

## 1.Schema Migrations:
### Upgrading (or potentially rolling back) an application and database schema version for each new version of app deployed.


## 2.Server Migrations:
### Moving your database from 1 server to another

## 3.Version Migration
### Upgrading from one major version of PostgreSQL to another

## 4.DBMS Migration
### Switching from MySQL or Oracle to PostgreSQL …


## Creating Migration:

```
$ npm install db-migrate
```

## Running Migrations
```
$ node node_modules/db-migrate/bin/db-migrate
```
## Undoing Migrations
### With migration you can revert to old state by just running a command
```
$ node_modules/.bin/sequelize db:migrate:undo
```
