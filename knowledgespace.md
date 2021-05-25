Knowledge Space
===============

...

# Principles

- In the *knowledge space*, everything is digitally expressed and communicated in formal logic, in a manner that humans can understand and computers can interpret
- These formal logic statements are written using a universal and extensible vocabulary, so any two statements can be interpreted together and there are no restrictions in what can be expressed
- These statements are expressed and communicated in small atomic *knowledge packages*, making each package individually reusable and referenceable
- Each knowledge package comes with rich provenance and metadata, including information about who created it
- Knowledge packages can include a digital signature of their creator
- Each knowledge package is represented by a unique and unforgeable content-based identifier
- Knowledge packages are thereby immutable, and any change of the content leads to a new knowledge package
- People can interact with the knowledge space via different kinds of web-based *knowledge services*
- *Publishing services* allow users to permanently publish their packages to make their knowledge available to the world
- *Lookup services* return the content of a knowledge package for a given package identifier
- Different kinds of *query services* return knowledge package references or aggregated values for specific parametrizable queries on specified subsets of all published knowledge packages
- A knowledge package is considered published once it is openly available on several independent web servers in a setting that allows for and encourages further replication and archiving by other servers
- Relevant entities, including knowledge package creators and knowledge services, are introduced to the knowledge space by publishing knowledge packages that describe them


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

