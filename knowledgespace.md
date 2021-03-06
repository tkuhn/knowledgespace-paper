Knowledge Space
===============

# Principles

- In the *knowledge space*, everything is expressed and communicated in formal logic, in a manner that humans can understand and computers can interpret, using a universal and extensible vocabulary
- Statements in the knowledge space are expressed and communicated in small *knowledge packages*, making each package individually reusable and referenceable
- Each knowledge package comes with provenance and metadata, including information about who created it
- Each knowledge package is represented by a unique and unforgeable content-based identifier
- A *knowledge package collection* is expressed by linking a collection identifier to the identifiers of the knowledge packages it contains, and by representing these links in knowledge packages themselves
- Users of the knowledge space are called *knowledge agents* and include people as well as automated agents
- A knowledge package can include a digital signature by the knowledge agent that created it, covering the rest of the knowledge package's content
- A knowledge package can include a declaration that it retracts or supersedes another knowledge package, thereby allowing for the representation of updates
- Knowledge agents can interact with the knowledge space via different kinds of online *knowledge services*
- Relevant entities, including knowledge agents and knowledge services, are introduced to the knowledge space by publishing knowledge packages that describe them, which are called *introduction records*
- An introduction record for a knowledge agent should include the public keys the knowledge agent uses to sign knowledge packages
- An introduction record of a knowledge service should include the nature of the service, the kind of knowledge packages it covers, the conditions under which knowledge agents may use it, and how it can be accessed
- A *publishing service* is a kind of knowledge service that allows knowledge agents to permanently publish knowledge packages
- A *lookup service* is a kind of knowledge service that returns the content of a knowledge package for a provided package identifier
- A *query service* is a kind of knowledge service that returns data, possibly aggregated, from published knowledge packages by executing a specified query for the provided parameter values
- A knowledge package is considered published once it is openly available via several independent lookup services in a setting that allows for and encourages further replication and archiving by others
- For all important kinds of knowledge services, there are always several independent service instances available
- Knowledge agents can provide assessments of entities by expressing a qualified link (such as a link representing approval) to an introduction record of the assessed entity, and by publishing this link as a knowledge package
- A *knowledge setting* is an entity described in an introduction record with the intention to serve as a starting point for establishing trust by providing references to other trusted entities
- A knowledge setting includes references to collections of introduction records of trusted knowledge agents and knowledge services, and specifies a trust range algorithm
- A *trust range algorithm* specifies which knowledge agents and services, and ultimately which knowledge packages should be considered trustworthy, given a knowledge setting and the published knowledge packages
- A knowledge agent is free to choose which knowledge setting to use, and define a new one if needed
- The execution of a trust range algorithm can be performed locally under the knowledge agent's control, or it can be delegated to trusted query services given that they support providing the knowledge setting as an argument

# Process

- ...
- If a knowledge agent has a trusted knowledge setting, it can extend the range of trust by searching trusted query services for assessments expressed by trusted knowledge agents to discover further knowledge agents and services that might deserve to be considered trusted too
- ...


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

