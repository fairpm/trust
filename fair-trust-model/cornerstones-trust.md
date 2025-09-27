# Cornerstones of Trust

| Document |            |
| -------- | ---------- |
| Status   | DRAFT      |
| Date     | 2025-09-27 |


## Components of Trust
FAIR’s Trust Model comprises an evaluation of three basic areas of trust: security, identity, and best practices, all of which begin with and rest upon Provenance.

### Security
> "The moral is obvious. You can't trust code that you did not totally create yourself. … No amount of source-level verification or scrutiny will protect you from using untrusted code."
>
> &#8212; Ken Thompson, [Reflections on Trusting Trust](https://dl.acm.org/doi/pdf/10.1145/358198.358210)

The most basic (and arguably most important) level of trust is established through robust security practices. A variety of automated checks are performed to ensure that the package and the repository that distributes it meets at least the established minimum criteria, as updated from time to time.

Security concerns are considered through the entire supply chain to ensure that none of its Nodes are vulnerable to known supply chain attack vectors.

[The abstract](https://dl.acm.org/doi/10.1145/358198.358210) for Thompson's 1984 lecture quoted above is simple:
>   To what extent should one trust a statement that a program is free of Trojan horses? Perhaps it is more important to trust the people who wrote the software.

Since no amount of security review can provide absolute certainty, we also need other means of establishing trust in the people who wrote the software.

### Identity
> Accountability fuels trust.

Identity is a very strong Trust Signal, as verified identity enables accountability, which fuels trust. Identity may be established through a pseudonym, if that pseudonym has an established reputation. Online, specific usernames or “handles” are associated with verifiable individuals. 

The FAIR Trust Model considers what can be known about the Publisher or Author(s) who create, maintain, and distribute the package. A verifiable identity can be linked to an established reputation within the ecosystem, or help to establish one. Most verifiable identity-based trust is traceable back to a human interaction to verify someone’s identity or the veracity of statements made about the individual or organization. For example, Bluesky verifies the identity of certain accounts, making their PLC:DID verifiable to a known individual without exposing any personal information.

FAIR does not store personal information through any of its idenity validation processes. FAIR will rely primarily third-party validators whom the user has already trusted with their information. Once the user’s identity has been validated, it is trusted as a verified identity, and does not need continual reverification against stored personal information. In any cases where FAIR accesses or requests personal information for verification purposes, the information is not stored; once it is verified, the user’s ID is marked as such and no personal information need be stored.

**To Determine for Technical Spec:** Detemine what Verifiable Identity platforms and third-party providers could be supported, and what other means of identity verification may be available to validate attestations from the Provenance Document.

### Best Practices
> Consistent adherence to best practices builds reputation. In Open Source, reputation is currency.

A variety of cues can be evaluated to infer how conscientious the Author(s) or Publisher may be in creating and distributing the Package and supporting its Users in much the same way as the [Van Halen test](https://en.wikipedia.org/wiki/Van_Halen_test) was used to indicate potential safety concerns. These cues may include factors like code quality and the presence (or absence) of optional metadata about the Package.

In some cases, optional metadata may be necessary for distribution into or use of the Package within certain legal jurisdictions, and best practices would suggest that this metadata should therefore be provided in all cases. Evaluating best practices may also consider established behaviour such as responsiveness to end user support requests and maintenance activity for the Package. While many of these tests may have no objective impact on the security or suitability of a package for a given purpose, they do provide subjective cues for establishing and building trust.

The importance of best practices as an indicator of security is reflected in the [Open Source Security Foundation](https://openssf.org/)'s [Best Practices Badge Program](https://www.bestpractices.dev/en) (OpenSSF [Best Practices WG on GitHub](https://github.com/ossf/wg-best-practices-os-developers))and the Germany-based [OpenCode Badge Program](https://opencode.de/en/knowledge/software-index/badges-en) ([GitLab](https://gitlab.opencode.de/open-code/badgebackend)) as well as in [SymfonyInsight](https://insight.symfony.com/what-we-analyse) (designed primarily for risk detection).

**To Determine for Technical Spec:** Review existing badge programs and determine means of verifying adherence to best practices generally and within the WordPress ecosystem specifically, including which practices are to be evaluated for Trust Scoring.

## Provenance

Establishing Provenance for each Package is the key component in assigning trust. For package management, Provenance requires verifiable information that establishes its origin and history on its way to the end User. This includes details about where the Package's source code came from, how it was built, and by whom. The goal of establishing Provenance is to ensure that not only has the correct Package been delivered exactly as requested, but to increase the security and trustworthiness of the software supply chains by providing a way to verifiably connect it to its Publisher and Author(s). Provenance is commonly referenced with two different nuances. First, it may refer simply to something's _origin_, which is the primary goal of establishing Provenance at all. Second, it may refer to an unbroken (ideally verifiable) chain detailing each step in how something was passed from its _originator_ to the current holder. For example, with fine art, a painting's provenance refers to the chain of ownership between the original artist and its current owner. Failing to establish provenance in this way (perhaps it disappeared for 50 years and was rediscovered) means it must be authenticated through other methods. The FAIR Trust Model considers both aspects of Provenance. First and foremost, the Package must be validated as an exact bit-for-bit copy of what was requested. Secondly, the chain from the Publisher to the end user is considered both to establish a Trust Score for the Package and to create an accountability record, or audit trail, for how the how the Package was found and retrieved.

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

One possible example of a Provenance record stored by the Installer might be as follows:

```{
    "build": {
        “name”: “string”,
        "version": "1.4.2”,
        “sourceRepo”: “[source-repo-url]”,
        "digest": {
            "sha256": “string”,
            "sha512": “string”,
            "gitCommit": “string”,
        },
        “dependencies”: {
            "repository": "[url]",
            "ref": "refs/heads/main"
        },
        "resolvedDependencies": {
             "uri": "[uri]",
             "gitCommit": "7fd1a60b01f91b314f59955a4e4d4e80d8edf11d"
        }
    },
    "supplyChain": {
        "author": {
            “name”: “string”,
            “did”: "did:plc:ewvi7nxzyoun6zhxrhs64oiz",
            “trustScore”: “string”
        },
        "publisher": {
            “name”: “string”,
            "did:plc:ewvi7nxzyoun6zhxrhs64oiz",
            “trustScore”: “string”
        },
        "package": {
            “name”: “string”,
            "did:plc:ewvi7nxzyoun6zhxrhs64oiz",
            “trustScore”: “string”
        },
        "repository": {
            “name”: “string”,
            "did:plc:ewvi7nxzyoun6zhxrhs64oiz",
            “trustScore”: “string”
        },
        "aggregator": {
            “name”: “string”,
            "did:plc:ewvi7nxzyoun6zhxrhs64oiz",
            “trustScore”: “string”
        }
    }
    "timestamp": {
        “committed”: “1449675508”
        "retrieved": "1755129477"
    }
}
```

Shown in json format, this version of a Provenance Document has three sections. The first is supplied by the Publisher, and records the Package's build details and dependencies. The second is appended by the Installer with data from the Trust Labeller, and records a DID and Trust Score for each Entity in the specific supply chain used to install the Package, including each Entity that would either have the capacity to modify the package or direct a user to an alternate source. The third section records a timestamp for the original Package build or commit from the Publisher and the timestamp for its retrieval for installation, which is added by the Client/Installer.

Provenance is therefore shown from the Package's origin through each connection to the end User, including timestamps, a Git commit ID, and Trust Scores for each entity in the chain at the moment the package is downloaded. This information together establishes accountability. Should a corrupt or malicious Package be received by the end User, the checksum should fail, and the Installer will abort the installation. If a malicious Package is inserted anywhere in the chain, it should similarly fail to install. The audit trail portion of the Provenance record can still be generated, recording the short list of Entities which will need investigation.

**To Determine for Technical Spec:** review and draft or adopt an existing standard format for the Provenance Document, such as the [in-toto Attestation Framework](https://github.com/in-toto/attestation) and the [SLSA model](https://slsa.dev/spec/v1.2-rc1/attestation-model), including its [Verification Summary Attestation (VSA)](https://slsa.dev/spec/v1.2-rc1/verification_summary). Appending the supply chain audit record to the Provenance Document is a FAIR-specific requirement, and it may be advantageous to use an existing standard for the Provenance Document with a separate recording of the audit record.

**For Consideration:** in the event that the signature or checksum for the Package fails, the download could be re-attempted to ensure that the failure was not due to a corrupt download. If it fails a second timme, an automated reporting of the incident might be considered whereby the audit trail for the aborted installation is sent to FAIR for security review of the entities in the chain.
