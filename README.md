# An LLM-Powered Chatbot MCP Client written in TypeScript

See the [Building MCP clients](https://modelcontextprotocol.io/tutorials/building-a-client) tutorial for more information.

## How to Configure
1. Install Node JS v16 or later
2. Create an Atlas Service Account with at least Project Owner role (this is to further restricted for Production environment)
3. Clone .env.example as .env file
4. Update ANTHROPIC_API_KEY, ATLAS_API_CLIENT (from the service account), ATLAS_API_SECRET (from the service account), and ATLAS_URI variables
5. Ensure your Admin API is allowed from your IP

## How to Run
1. Run ```npm run-script build```
2. Run ```node build\index.js```

Then you will see this 
```
Connected to server with tools: [
  'atlas-list-clusters',
  'atlas-list-projects',
  'atlas-inspect-cluster',
  'atlas-create-free-cluster',
  'atlas-create-access-list',
  'atlas-inspect-access-list',
  'atlas-list-db-users',
  'atlas-create-db-user',
  'atlas-create-project',
  'atlas-list-orgs',
  'atlas-connect-cluster',
  'switch-connection',
  'list-collections',
  'list-databases',
  'collection-indexes',
  'create-index',
  'collection-schema',
  'find',
  'insert-many',
  'delete-many',
  'collection-storage-size',
  'count',
  'db-stats',
  'aggregate',
  'update-many',
  'rename-collection',
  'drop-database',
  'drop-collection',
  'explain',
  'create-collection',
  'mongodb-logs'
]

MCP Client Started!
Type your queries or 'quit' to exit.

Query:
```

## Sample queries

* show me all the clusters
* 
