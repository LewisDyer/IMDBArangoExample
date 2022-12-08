# IMDBArangoExample
Example with ArangoDB using the IMDB dataset with some data cleaning.

Source files from https://github.com/arangodb/example-datasets/tree/master/Graphs/IMDB, with some sanitising (making a new cleaner graph, in particular splitting off different edge and vertex types into new connections)

## Setup instructions

### Restore dump

`arangorestore --server.endpoint tcp://<host>:<port> --server.database IMDB --create-database --include-system-collections`

### Create new dump

`arangodump --server.endpoint tcp://localhost:8529 --server.database IMDB --include-system-collections --collection _graphs --collection actsIn --collection directed --collection Genre --collection hasMovie --collection Movie --collection Person --compress-output false --envelope true`