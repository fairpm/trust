# Cornerstones of Trust

| Document |            |
| -------- | ---------- |
| Status   | DRAFT      |
| Date     | 2025-09-13 |


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

### Best Practices
> Consistent adherence to best practices builds reputation. In Open Source, reputation is currency.

A variety of cues can be evaluated to infer how conscientious the Author(s) or Publisher may be in creating and distributing the Package and supporting its Users in much the same way as the [Van Halen test](https://en.wikipedia.org/wiki/Van_Halen_test) was used to indicate potential safety concerns. These cues may include factors like code quality and the presence (or absence) of optional metadata about the Package.

In some cases, optional metadata may be necessary for distribution into or use of the Package within certain legal jurisdictions, and best practices would suggest that this metadata should therefore be provided in all cases. Evaluating best practices may also consider established behaviour such as responsiveness to end user support requests and maintenance activity for the Package. While many of these tests may have no objective impact on the security or suitability of a package for a given purpose, they do provide subjective cues for establishing and building trust.

## The Foundation of Trust: Provenance





