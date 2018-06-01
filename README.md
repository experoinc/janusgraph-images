# JanusGraph Docker Images #

Repository for building and publishing [JanusGraph][JG] docker images.

# Building #

The `build-images.sh` script will build the docker images for all the Dockerfiles in the versioned
folder directories.

# Publishing #

The `push-images.sh` script will push the docker images for all the versioned folders in the repo.

Prior to publishing, you'll need to login to [Docker Hub][DH] using the `docker login` command.

# Configuration #

The docker containers are configured through environment variables. The environment variables are 
structured to reflect the different configuration properties available in the 
[JanusGraph Configuration][JG_CONFIG] .

**Example**

| Configuration Key       | Environment Variable        |
| ----------------------- | --------------------------- |
| storage.backend         | JANUS_STORAGE_BACKEND       |
| storage.cql.keyspace    | JANUS_STORAGE_CQL_KEYSPACE  |
| index.search.backend    | JANUS_INDEX_SEARCH_BACKEND  |


In general, a configuration parameter of the form `chained.property.path` will take the form
`JANUS_CHAINED_PROPERTY_PATH`. The environment variable will be prefixed with `JANUS` and the 
hyphens and periods in the name of the property key are replaced with underscores. Lastly, the
characters in the property path are converted to uppercase.

# Running #

There are `docker-compose.yml` files demonstrating various configurations in which the JanusGraph
image can be used. 


[JG]: http://janusgraph.org/
[JG_CONFIG]: https://docs.janusgraph.org/latest/config-ref.html
[DH]: https://hub.docker.com/