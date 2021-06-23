# Node Sequelize CLI

- Learning Sequelize CLI with PostgreSQL in NodeJS backend
- Tutorial by: Jan Göbel (productioncoder)
  - [Node Sequelize tutorial with Postgres | Sequelize migrations and seed data](https://www.youtube.com/watch?v=Eu-h3iUk45o)

## Bootstrapping

- Install basic `sequelize` dependencies (`sequelize`, `pg`, `pg-hstore`)
- Install the `sequelize-cli`
- Bootstrap the project with the Sequelize CLI: `npx sequelize-cli init`

## Database Configuration

_./config/config.json_

```json
{
  "development": {
    "username": "postgres",
    "password": "123456",
    "database": "sequelize_cli",
    "host": "127.0.0.1",
    "dialect": "postgres"
  }
}
```

> For production applications instead of this `config.json` create **config.js** and export the configurations. We can then use envornment variables in the same using `dotenv`

## Creating Models

- We can create models from the Sequelize CLI
  ```bash
  npx sequelize-cli model:generate --name User --attributes firstName:string,lastName:string,email:string
  ```
- This will create:
  - a model file at: _./models/user.js_
  - a migration file at: _./migrations/XXXXXXXXXXXXXX-create-user.js_
- Note:
  - Every model is like a table in our database. The model here is a javascript class.
  - The migration has two functions:
    - `up`: Apply the migrations
    - `down`: Undo the migrations
  - We can manually update the migration file to fit our needs
