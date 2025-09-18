# Building a FAIR Trust Model

| Document |            |
| -------- | ---------- |
| Status   | DRAFT      |
| Date     | 2025-09-13 |

## Preamble

The [moderation, or labelling specification](https://github.com/fairpm/fair-protocol/tree/main/docs/moderation) section of the [FAIR Protocol](https://github.com/fairpm/fair-protocol) specifies that all nodes in the network must subscribe to FAIR’s Trust Labelling service. The Trust Labeller evaluates cues based on a list of automated checks and human review to provide an objective trust score for each package being viewed or installed. This mechanism leaves the end user free to install “untrusted” packages, based perhaps on their own knowledge of its source. In addition, the labelling architecture allows for the creation of labellers by third parties, to which node operators or end users can optionally subscribe.

## Prior Art

Open Source is famously based upon the concept of “standing on the shoulders of giants,” and the FAIR Trust Model is influenced by other work in broad areas of trust, including where those other efforts may have a different focus. For example, the [SLSA](https://slsa.dev/) addresses individual builds, or Package releases for supply chain threats in four areas: source, build, dependency, and usage. In Germany, the [Open Code Badge Program](http://badges.opencode.de/en/) checks repositories to assign badges based on their rating of specific criteria as a means of building trust in Open Source software. The program examines security, Open Source licensing, software reuse, and maintenance and awards a bronze, silver, or gold badge for each area.

## Approach

In [considering other package management systems](https://github.com/fairpm/fair-protocol/blob/main/docs/initial-design.md) (prior art) for the FAIR architecture design, FAIR found that while each has its strengths within its own context, none were comprehensive enough to address a fully decentralized Package distribution system. FAIR’s Trust Model is designed to extend beyond the Package itself to include Nodes and Entities within the federated network. Since FAIR sets out to improve both security and trust for WordPress packages over the ecosystem’s previous centralized distribution model, it begins with the same types of automated scans used for the WordPress.org repositories and builds upon them.

FAIR’s current priorities do not include a full-scale evaluation of the criteria for adding Packages to Federated Repositories, and will largely use the existing [WordPress plugin guidelines](https://developer.wordpress.org/plugins/wordpress-org/detailed-plugin-guidelines/), [plugin review handbook](https://make.wordpress.org/plugins/handbook/), and [theme review guidelines](https://developer.wordpress.org/themes/releasing-your-theme/theme-review-guidelines/) as its starting point until such time as the WordPress community is able to provide broad-based feedback concerning any changes it would like to see. While requirements for hosting of Packages in the Federated network will be more stringent, some of the existing rules are expected to become more relaxed in specific areas. For example, FAIR’s roadmap includes allowing paid Packages to be downloadable from Federated Repositories with validated license keys.

## Overview Diagram

As described here, the Trust Model and its implementation takes this general format for creating a Trust Score to use in assigning a Trust Label to a Package based on scripted evaluation of the Package itself (internal) and checks against external verification sources.

<img width="860" height="660" alt="FAIR Packaging Trust drawio" src="https://github.com/user-attachments/assets/b4b244af-44e5-4390-ba31-d42c95eb7177" />
