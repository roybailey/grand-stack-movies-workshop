# GRAND Stack Workshop

## Workshop Steps Completed

* Cloned `https://github.com/grand-stack/grand-stack-movies-workshop`
* Downloaded recommendations database (see Setup Neo4j recommendations database)
* Ran the GraphQL template
* Ran the react-apollo template
* Modified the react-apollo template to point to local GraphQL instance
* Modified the GraphQL moviesByTitle to take `title` instead of `subString`
* Modified the react-apollo to call `moviesByTitle`

#### Setup Neo4j recommendations database

```
curl https://s3.amazonaws.com/neo4j-sandbox-usecase-datastores/v3_2/recommendations.db.zip > /tmp/recommandations.zip
unzip recommendations.zip
mkdir -p neo4j/data/databases/
mv recommendations.db neo4j/data/databases/graph.db
docker run \
  --publish=7474:7474 --publish=7687:7687 \
  --volume=./neo4j/data:/data \
  neo4j:3.2.3
``` 

```
export NEO4J_URI=bolt://localhost:7687/
export NEO4J_USER=neo4j
export NEO4J_PASSWORD=<your value here>
```

## What is GRAND stack?

**G**raphQL, **R**eact, **A**pollo, **N**eo4j **D**atabase. The GRAND stack is a combination of modern technologies for building scalable applications for the web and mobile.

## Overview

The goal of this workshop is to build a simple movie recommendation web application making use of the GRAND stack.

![](img/webappoverview.png)


The basic requirements are:

* Allow the user to search for movies by title
* Show movie details for each movie matching the search string
* Show other recommended movies for each matching movie

![](img/webappoverview-reqs.png)


// App architecture overview

This workshop covers

* Modeling and querying data in Neo4j, including writing Cypher queries for generating personalized movie recommendations
* Building a GraphQL API, including defining a schema, types, and queries, backed by Neo4j
* Designing a React user interface frontend for searching and displaying movie details, including recommended movies
* Using the Apollo Client integration

and is divided into three sections. Each section has a beginning skeleton state, but requires implementing some missing functionality before moving on to the next section. It is recommended to complete the workshop sections in the following order:

1. **[Neo4j Database](/neo4j-database)**
1. **[GraphQL](/graphql)**
1. **[React / Apollo](/react-apollo)**

The workshop can be completed using the following hosted/demo service, without having to worry about setting up a local development environment (a link to the beginning skeleton state for each section is included in the README for each section):

* [Neo4j Sandbox](https://neo4j.com/sandbox-v2/)
* [Apollo Launchpad](https://launchpad.graphql.com/new)
* [Code Sandbox](https://codesandbox.io/)


 or can be completed using standard developer tools by cloning this repository.

To begin the workshop, begin the **[Neo4j Database](/neo4j-database)** section.
