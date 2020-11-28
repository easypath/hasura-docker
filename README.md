# hasura-docker
[Hasura GraphQL Engine](https://hasura.io/) running on Docker.

## Prerequisites:
- A running [PostgreSQL](https://github.com/easypath/postgres-docker) instance

## Usage:
- Copy the sample config file:
  ```
  cp .env.sample .env
  ```

- Edit the config file and set the following values:
  ```
  HASURA_GRAPHQL_DATABASE_URL=postgresql://username:password@postgres-db:5432/database
  HASURA_GRAPHQL_ENABLE_CONSOLE=true
  HASURA_GRAPHQL_ADMIN_SECRET=myadminsecretkey
  ```

- Launch the container:
  ```
  ./start-container.sh
  ```

- Verify you can log into the Hasura Console: [http://localhost:8080](http://localhost:8080)


## Miscellaneous
- This docker-compose file creates a private Docker network locally called `db-network-private` - you can connect other containers directly to this network and the GraphQL API will be available at `http://graphql-api:8080/v1/graphql`
