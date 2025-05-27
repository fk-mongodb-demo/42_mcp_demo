# An LLM-Powered Chatbot MCP Client written in TypeScript

Refer to MongoDB MCP Server [Blog](https://www.mongodb.com/blog/post/announcing-mongodb-mcp-server).

The MongoDB MCP Server enables developer tools with MCP clients to interact directly with a MongoDB database and to handle a range of administrative tasks, such as managing cluster resources, as well as data-related operations like querying and indexing.

![image](https://github.com/user-attachments/assets/6bf1f29b-66cc-41f1-975a-a05c6eb161cc)

The MongoDB MCP Server enables:
1. Effortless data exploration: Ask your AI to "show the schema of the 'users' collection" or "find the most active users in the collection."
2. Streamlined database management: Use natural language to perform database administration tasks like "create a new database user with read-only access" or "list the current network access rules."
3. Context-aware code generation: Describe the data you need, and let your AI generate the MongoDB queries and even the application code to interact with it.

Checkout the GitHub repo https://github.com/mongodb-js/mongodb-mcp-server (currently v0.1.1)

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
* get me all projects
* give me all databases under project with ID 6835a0d9d17074609628eb73 and cluster Cluster0
* tell me more about Cluster0 project with ID 6835a0d9d17074609628eb73
* give me all users under project with ID 6835a0d9d17074609628eb73
* create new db user with username test and password test1234 as reader for project with ID 6835a0d9d17074609628eb73
* find 5 documents in sample_restaurants database and restaurants collection with cuisine:American
* create new collection 'test123' in database 'testdb'
* insert new document with 2 fields; id:1 and code:2 in collection named 'test123' in the database 'testdb'
