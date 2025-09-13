# Definitions

| Document | |
| -- | -- |
| Status | Draft |
| Date | 2025-09-13 |

## Terminology Used in the FAIR Trust Model


### Attestation
Attestation is an authenticated statement (metadata) about a Package or collection of Packages, such as would be found in a Provenance Document.

### Author
An Author is the creator of a Package. With software, an Author is typically a software developer. Packages may have more than one Author.

### Contributor
A Contributor is roughly equivalent to an Author, with the stipulation that a Contributor is not the sole Author of a Package.

### Entity
An Entity in this document refers to a package, person, organization, system, or Node within the FAIR network to which a Trust Score may be assigned. It is an intentionally vague term, and may include Developers (Authors or Contributors), Users, Publishers, Corporations, or organized groups.

### FAIR
Federated And Independent Repositories (FAIR). When capitalized as an acronym, the unqualified term may refer to the FAIR Web Foundation or its working groups, including its Technical Steering Committee. Context should usually dictate clearly enough. When used with normal grammatical capitalization ("Fair" or "fair"), the term should be understood in the normal usage of the word.

### FAIR Protocol
The FAIR Protocol refers to part or all of the specifications authored by FAIR to govern its operation. This may include drafts and working documents, as well as other protocols or specifications by extension.

### Federation
Federation is the process of a group of groups or individuals associating together for a common purpose. In the context of FAIR, Federation is for the purpose of distributing Packages. Anyone may connect to Federated sources to download Packages, but publishing Packages to the Federated network requires approval through a vetting process.

### Node
In telecommunications, a Node is a communications endpoint. In networking, it includes the concept of repeaters, and this general definition carries into computing environments, so that a Node in a distributed system refers to an end point represented by a client or a server, or a repeater or redistribution point. WIthin the FAIR network architecture, it retains this nonspecific meaning, and includes Repositories, Aggregators, Clients, Labellers, and any other digital endpoint with an electronic connection to the federated network. “Node” is from the Latin nodus, or “knot” – Nodes tie everything together.


### Provenance


### Provenance Document


### Publisher
A Publisher is an entity that publishes, uploads, or distributes a Package through a Federated Repository. A Publisher must hold the copyright to or valid license permitting distribution of the Package. A Publisher may also be an Author.

### Trust Score
Within FAIR, a Trust Score is a numerical representation of how much trust has been established for an Entity. The score is dynamic and subject to change at any time according to automated evaluation of Trust Signals or manual review.

### Trust Signals
Trust Signals are the various indicators used in the FAIR Trust Model to calculate a Trust Score and apply a Trust Label to an entity. Trust Signals include both “hard” and “soft” measures, and may carry different weighting in the calculation of the Trust Score. Required Trust Signals are treated as Pass/Fail measures. Only some of the optional Trust Signals will trigger a negative adjustment to the Trust Score.

### Trust Label
Trust Labels are user-facing indicators assigned by the FAIR Trust Labeller. These may be a numerical value or a string indicating a specific state such as "Defederated", "Insecure", "Fraudulent", or other indicators to be determined. The requirement for all Nodes in the FAIR network to subscribe to the FAIR Trust Labeller is for the express purpose of ensuring that these labels are displayed to Administrator Users at every Node.

### User
Within FAIR, Users may include developers, system administrators, or end users, who may be website owners, maintainers, or site visitors. For clarity, within this proposal, the unqualified term “user” refers to administrators of WordPress websites.

### VDP
Vulnerability Disclosure Program, a structured process for the responsible reporting of software security vulnerabilities to its maintainer(s).








