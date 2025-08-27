# FAIR Supply Chain Overview

| Document   |               |
| ---------- | ------------- |
| Purpose    | WG Resource   |
| Status     | Draft         |

## Entities in the FAIR Supply Chain

Not all of these entities are specifically defined in the FAIR protocol as of this writing, however they do exist in the supply chain. The 'FAIR Supply Chain' diagram below shows different types of entities which are a part of the FAIR ecosystem, whether or not they are a direct part of the supply chain, indicated here by bold red lines.

| FAIR Supply Chain Entities |
| -------------------------- |
| <img width="1938" height="1050" alt="FAIR_Supply_Chain" src="https://github.com/user-attachments/assets/94ed9a92-be97-43f6-9b09-27874209f1b2" /> |

### Notes to FAIR Supply Chain Entities Diagram

- **Author & Publisher**
  - May be the same entity.
  - Multiple Authors may exist for a Package (Authors ≍ Contributors).
  - A Publisher is the entity making the Package available for distribution.
  - An Author may also be the Publisher.
  - A Package will have a single Publisher.
  - A Publisher may or may not be a "vendor", a no distinction is made here for whether or not a financial transaction occurs.
  - _The Publisher must hold the copyright OR a license from the Author(s) to distribute the package._
- **Package**
  - A Package could be any digital file distributed in the FAIR network, but primarily assumed to be a WordPress plugin, theme, or WordPress core. These may include alternates such as the WordPress distribution offered by FAIR which includes the FAIR Plugin preinstalled, or a fork such as ClassicPress.
- **WordPress.org (Grey Circle)**
  - WordPress.org is shown in a grey circle since it maintains a specific trust level internally for the packages it distributes from its Repository. In a monolithic single-source system, some of the trust signals between the entities within the system may be opaque, but have been established in some form between Authors, Publishers, and the Repository.
- **Mini-FAIR Repo**
  - FAIR publishes the Mini-FAIR Repo plugin for WordPress to make one or more Packages available to the FAIR network (_e.g._, to Aggregators & Client/Installers) for installation or update from its canonical source. Although any package _could_ be distributed this way, it is generally intended for use by the Author/Publisher directly to distribute their Package(s).
- **FAIR Repository**
  - Represents a future project to build a repository to distribute packages using the FAIR protocol in a similar fashion but on a much larger scale than the Mini-FAIR Repo plugin. This type of repository would be presumed to distribute Packages on behalf of Publishers who do not wish to manage their own Mini-FAIR Repo or who may want greater visibility offered by the selected FAIR Repository.
- **AspireSync / AspireBuild**
  - These projects are internally-used build tools to manage the creation and update of the AspirePress Mirror of the WordPress Repository, and are not end-user-facing. AspireSync is in production, with AspireBuild in the planning stage to eventually replace AspireSync while extending the operations is performs.
- **WordPress.org Mirror**
  - Operated by AspirePress & FAIR, this offers Packages represented as true copies fo those in the WordPress repository.
- **AspireCloud & FAIR Aggregator**
  - AspireCloud functions as a (currently) unique type of FAIR Discovery Aggregator, indexing (aggregating) not only FAIR Repositories, but the "legacy" Packages from the WordPress Mirror.
- **FAIR Aggregator**
  - FAIR Aggregators will present searchable indexes of FAIR Repositories. Future implementations _may_ allow Aggregators to index (aggregate) legacy WordPress Repository packages via AspirePress, which will translate the package index to use the FAIR Protocol rather than the WordPress API, so individual Aggregators won't need to do this themselves.
- **Bluesky & FAIR PLC Servers**
  - A FAIR PLC Server is not currently on the planned roadmap, however it is envisioned that FAIR will at some point operate its own PLC Server, which may be mirrored or federated with Bluesky's.
- **Telemetry (Analytics)**
  - Not yet in scope, but telemetry collected centrally is intended to allow statistical telemetry to be shared publicly and to present useful information to Authors, including install counts, environment (platform), and browser usage statistics. These will be anonymized and aggregated to enable maximum transparency in what is collected and shared while maintaining privacy for users of all types.
- **Not Shown**
  - Translations and Block Patterns would also be packages, but are not yet in scope here.
  - AspireCloud will assign a Web:DID to each Package it distributes from the WordPress Repository Mirror, enabling "legacy" Packages to be searched and installed using the FAIR Protocol.

## Connections in the FAIR Supply Chain

The following 'FAIR Supply Chain Connections' diagram shows how different systems or entities connect to one another for various data exchange purposes. Different types of connection are shown with different colours and formats for the connecting lines. At this stage, no strong distinction should be made between arrows indicating unidirectional or bidirectional connections. Each type of connection represents a potential attack vector, but also represents opportunities for improving security in other areas.

| FAIR Supply Chain Connections |
| ----------------------------- |
| <img width="1938" height="1050" alt="FAIR_Supply_Chain_Connectors" src="https://github.com/user-attachments/assets/607c0b96-82f9-4eca-99c2-ba14935edf06" /> |

### Notes to FAIR Supply Chain Connections Diagram

- **PLC Server Connections**
  - DID lookups to facilitate retrieval of the DID Document.
- **FAIR Network Connections**
  - Flow of data between nodes, whether Package Meta or Packages themselves.
- **FAIR Labelling Connections**
  - FAIR-applied Trust labels are required, and are the broad purpose for this WG.
  - Non-FAIR-applied labels are optional, whether or not they are trust signals. These can also include factual classifications like a taxonomy, third-party recommendations, status items, or any number of other labels.
- **FAIR Telemetry Connections**
  - FAIR will collect telemetry data for aggregation at various points.


