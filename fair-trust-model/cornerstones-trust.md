# Cornerstones of Trust

| Document |            |
| -------- | ---------- |
| Status   | DRAFT      |
| Date     | 2025-12-07 |


## Components of Trust
FAIR’s Trust Model comprises an evaluation of three basic areas of trust: security, identity, and best practices, all of which begin with and rest upon Provenance.

### Security
> "The moral is obvious. You can't trust code that you did not totally create yourself. … No amount of source-level verification or scrutiny will protect you from using untrusted code."
>
> &#8212; Unix Co-creator Ken Thompson, [Reflections on Trusting Trust](https://dl.acm.org/doi/pdf/10.1145/358198.358210)

The most basic (and arguably most important) level of trust is established through robust security practices. A variety of automated checks are performed to ensure that the package itself and the repository that distributes it meets at least the established minimum criteria, as updated from time to time.

Security concerns are considered through the entire supply chain to ensure that none of its Nodes are vulnerable to known supply chain attack vectors.

[The abstract](https://dl.acm.org/doi/10.1145/358198.358210) for Thompson's 1984 lecture quoted above is simple:
>   To what extent should one trust a statement that a program is free of Trojan horses? Perhaps it is more important to trust the people who wrote the software.

Since no amount of security review can provide absolute certainty, we also need other means of establishing trust in the people who wrote the software.

### Identity
> Accountability fuels trust.

Identity is a very strong Trust Signal, as verified identity enables accountability. Identity may be established through a pseudonym, if that pseudonym has an established reputation. Online, specific usernames or “handles” are associated with verifiable individuals.

The FAIR Trust Model considers what can be known about the Publisher, Author(s) (Contributors) and Maintainer(s) who create, maintain, and distribute the package. FAIR's Trust Model anticipates that a verifiable identity can be linked to an established reputation within the ecosystem, or help to establish one. Most verifiable identity-based trust is traceable back to a human interaction to verify someone’s identity or the veracity of statements made about the individual or organization. For example, Bluesky verifies the identity of certain accounts, making their PLC:DID verifiable to a known individual without exposing any personal information. (This process is behind the familiar "blue checkmark" icon for certain accounts like those for the accounts of journalists and prominent public individuals.)

FAIR does not intend to store personal information through its idenity validation processes beyond what the dislosures of its Privacy Policy. Wherever possible, FAIR will rely primarily on third-party validators that the user has already trusted with their information. Once the user’s identity has been validated, it is trusted as a verified identity, and does not need continual reverification against stored personal information. In any cases where FAIR accesses or requests personal information for verification purposes, the information is not stored; once it is verified, the user’s ID is marked as such and no personal information need be stored.

### Best Practices
> Consistent adherence to best practices builds reputation. In Open Source communities, reputation is currency.

A variety of cues can be evaluated to infer how conscientious the Author(s) or Publisher may be in creating and distributing the Package and supporting its Users in much the same way as the [Van Halen test](https://en.wikipedia.org/wiki/Van_Halen_test) was used to indicate potential safety concerns. These cues may include factors like code quality and the presence (or absence) of optional metadata about the Package.

In some cases, optional metadata may be necessary for distribution into or use of the Package within certain legal jurisdictions, and best practices would suggest that this metadata should therefore be provided in all cases. Evaluating best practices may also consider established behaviour such as responsiveness to end user support requests and maintenance activity for the Package. While many of these tests may have no objective impact on the security or suitability of a package for a given purpose, they do provide subjective cues for establishing and building trust.

The importance of best practices as an indicator of security is reflected in the [Open Source Security Foundation](https://openssf.org/)'s [Best Practices Badge Program](https://www.bestpractices.dev/en) (OpenSSF [Best Practices WG on GitHub](https://github.com/ossf/wg-best-practices-os-developers))and the Germany-based [OpenCode Badge Program](https://opencode.de/en/knowledge/software-index/badges-en) ([GitLab](https://gitlab.opencode.de/open-code/badgebackend)) as well as in [SymfonyInsight](https://insight.symfony.com/what-we-analyse) (designed primarily for risk detection).

## Provenance

Establishing Provenance for each Package is the key component in assigning trust. For package management, Provenance requires verifiable information that establishes its origin and history on its way to the end User. This includes details about where the Package's source code came from, how it was built, and by whom. The goal of establishing Provenance is to ensure that not only has the correct Package been delivered exactly as requested, but to increase the security and trustworthiness of the software supply chain by providing a way to verifiably connect it to its Publisher. Provenance is commonly referenced with two different nuances. First, it may refer simply to something's _origin_, which is the primary goal of establishing Provenance. FAIR addresses this with a Provenance Document containing the Publisher's attestations for each Package.

Second, provenance may refer to an unbroken (ideally verifiable) chain detailing each step in how something was passed from its _originator_ to the current holder. For example, with fine art, a painting's provenance refers to the chain of ownership between the original artist and its current owner. Failing to establish provenance in this way (perhaps it disappeared for 50 years and was rediscovered) means it must be authenticated through other methods. The FAIR Trust Model considers both aspects of Provenance. First and foremost, the Package must be validated as an exact bit-for-bit copy of what was requested. Secondly, the chain from the Publisher to the end user is considered to create an accountability record, or audit trail, for how the how the Package was found and retrieved.

In the context of addressing the full supply chain, a complete Provenance record requires verifiable information about
  1. the Package’s origin, including information about its Publisher;
  2. how the Package was found and distributed to the end User (Aggregators, Repositories, or other Nodes); and
  3. whether the Package has been modified from its canonical source.

Package signing and validation resolves the security requirement to verify an exact copy of the Package requested from the Publisher, even if it has been cached or mirrored at some point in the chain, including by a CDN. A mismatch may override any trust signal.

This addresses the three areas required for the end User to establish trust
  1. in the Publisher;
  2. in every Node or Entity in the direct supply chain which has or may have the ability to modify, replace, or redirect requests concerning the Package or its metadata; and
  3. that the downloaded Package is an exact copy of what the Publisher provided, including that it was not corrupted in the download process.

Various solutions or schemas exist for communicating this information, generally pointing toward a specially-formatted Provenance Document included with each Package. The Provenance Document would include specific attestations about the Package, its creator(s), and its Publisher which can all be verified by FAIR to help establish a Trust Score.

Since the Provenance Document is composed by the Publisher of the Package and forms a part of the signed Package metadata, it cannot be modified before it is received by the Client/Installer, which will also verify the Package's original checksum and signature. Signing the metadata enables verification that it has not been modified in a way that could affect the Trust Score or the signature validation for the Package itself.

The contents of the Provenance Document are evaluated for the FAIR Trust Labeller and incorporated into a Trust Score for the Package with details concerning how it was calculated. At the time the Package is downloaded, the Client/Installer can record the DIDs for the Aggregator from which the Package was discovered and the Repository from which it was downloaded, together with a timestamp and the Trust Score for each Entity in the specific supply chain at the time the Package is downloaded. This information is to be stored with the installed Package to preserve an audit trail for accountability within FAIR, and may be appended to when the Package is updated.

Valid versions of the Provenance Document would need at least one Author _or_ Publisher, but no more than a single Publisher. In this context, Author and Contributor may be considered synonymous and include multiple individuals. Multiple Aggregators could exist in theory, but only the Repository from which the package was actually downloaded would be shown, even if it is available in other Repositories or Mirrors.

Provenance is therefore shown from the Package's origin through an audit trail showing each connection in the chain to the end User, including timestamps, a Git commit ID, and (eventually) Trust Scores for each entity in the chain at the moment the package was downloaded. This information together establishes accountability. Should a corrupt or malicious Package be received by the end User, the checksum and/or Package signature would fail, and the Installer will abort the installation. If a malicious Package is inserted anywhere in the chain, it would therefore fail to install, but the audit trail is still be generated. If the Package is determined to have been intentionally modified in transit, the audit record can provide a forensic record to help determine where the supply chain attack occurred.

**For Consideration:** in the event that the signature or checksum for the Package fails, the download could be re-attempted to ensure that the failure was not due to a corrupt download. If it fails a second timme, an automated reporting of the incident might be considered whereby the audit trail for the aborted installation is sent to FAIR for security review of the entities in the chain.
