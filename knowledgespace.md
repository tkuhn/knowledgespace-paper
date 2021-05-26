Knowledge Space
===============

...

# Principles

- In the *knowledge space*, everything is digitally expressed and communicated in formal logic, in a manner that humans can understand and computers can interpret
- These formal logic statements are written using a universal and extensible vocabulary, so any two statements can be interpreted together and there are no restrictions in what can be expressed
- These statements are expressed and communicated in small *knowledge packages*, making each package individually reusable and referenceable
- Each knowledge package comes with rich provenance and metadata, including information about who created it
- Each knowledge package is represented by a unique and unforgeable content-based identifier
- A *knowledge package set* is defined by linking the set identifier to the knowledge package identifiers of its elements and by publishing these links as knowledge packages themselves
- Knowledge packages can include a digital signature of their creator
- Users of the knowledge space are called *knowledge agents* and include people as well as automated agents
- Knowledge agents can interact with the knowledge space via different kinds of web-based *knowledge services*
- A *publishing service* is a kind of knowledge service that allows knowledge agents to permanently publish their packages to make their knowledge available to the world
- A *lookup service* is a kind of knowledge service that returns the content of a knowledge package for a given package identifier
- A *query service* is a kind of knowledge service that returns simple or aggregated values by executing a specified query on a specified subset of the published knowledge packages for the provided parameter values
- A knowledge package is considered published once it is openly available on several independent web servers in a setting that allows for and encourages further replication and archiving by other servers
- Relevant entities, including knowledge agents and knowledge services, are introduced to the knowledge space by publishing knowledge packages that describe them, which are called *introduction records*
- An introduction record for a knowledge agent should include the public keys the knowledge agent uses to sign knowledge packages
- Knowledge agents can provide assessments of entities by expressing a qualified link (such as a link representing approval) to an introduction record of the assessed entity, and by publishing this link as a knowledge package
- As a starting point for establishing trust, a *knowledge setting* is knowledge package that refers to a collection of introduction records of authoritative knowledge agents and knowledge services


# Knowledge Service Nodes

- Publishing Service
- Lookup Service
- Query Service
  - Core Information Service


# Knowledge Services

Prerequisites to reliably access the knowledge services:

- A setting, represented as a nanopublication, containing:
  - Identifier of an authority index
  - Identifier of a service index
  - Bootstrap URLs of lookup services
  - Scoring and conflict resolution algorithm
  - Update strategy

Steps to reliably access the knowledge services:

- Retrieve all descriptions from the authority index (np get -c)
- Retrieve agent endorsements ( * approves-of * / * npx:declaredBy * )
- Calculate agent scores (= number of independent paths; possibly + inverse average path length)
- Resolve agent conflicts (max. score) to determine authentic agent set
- Retrieve service endorsements ( * approves-of/disapproves-of * / * a NanopubService )
- Calculate service scores


# References

- White, Douglas R., and Mark Newman. "Fast approximation algorithms for finding node-independent paths in networks." (2001). https://dx.doi.org/10.2139/ssrn.1831790


# Vocabulary

- [AGENT] approves-of [NP]
- [AGENT] disapproves-of [NP]

