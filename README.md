# An LLM-Powered MongoDB MCP Demo Written in TypeScript

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

## Sample responses

Query: 
```
find 5 documents in sample_restaurants database and restaurants collection with cuisine:American
```

Response:
```
Query: find 5 documents in sample_restaurants database and restaurants collection with cuisine:American

I'll help you find 5 documents from the sample_restaurants.restaurants collection where the cuisine is American. I'll use the `find` tool with appropriate filter, limit, and collection parameters.
[Calling tool find with args {"database":"sample_restaurants","collection":"restaurants","filter":{"cuisine":"American"},"limit":5}]
Here's a more readable format of the 5 American restaurants found:

1. Riviera Caterer
- Borough: Brooklyn
- Address: 2780 Stillwell Avenue
- Zipcode: 11224
- Latest Grade: A

2. Brunos On The Boulevard
- Borough: Queens
- Address: 8825 Astoria Boulevard
- Zipcode: 11369
- Latest Grade: Z

3. Regina Caterers
- Borough: Brooklyn
- Address: 6409 11 Avenue
- Zipcode: 11219
- Latest Grade: A

4. The Movable Feast
- Borough: Brooklyn
- Address: 284 Prospect Park West
- Zipcode: 11215
- Latest Grade: A

5. Wild Asia
- Borough: Bronx
- Address: 2300 Southern Boulevard
- Zipcode: 10460
- Latest Grade: A

Distribution by Borough:
- Brooklyn: 3 restaurants
- Queens: 1 restaurant
- Bronx: 1 restaurant

Most restaurants (4 out of 5) have an 'A' grade in their most recent inspection, with only Brunos On The Boulevard having a 'Z' grade.
```
