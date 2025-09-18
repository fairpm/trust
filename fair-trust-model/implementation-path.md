# Implementation Path

## Trust Inheritance from WordPress Repository

Packages currently hosted in the official WordPress.org Repository will effectively be grandfathered into the FAIR Trust Model with trust inherited from the evaluation process by which the Package was accepted into the WordPress Repository. The existing metadata available for these Packages is not anticipated to be sufficient to determine a reliable trust score based on the proposed FAIR Trust Model, however this is addressed by the fact that the Package was previously vetted through a process including human review.

Publishers wishing to host their Package in a FAIR Repository may do so, and continue to inherit previously-earned Trust, since an active listing in the WordPress Repository is considered a strong Trust Score. Federation within FAIR will begin in a limited fashion to ensure trust can be built and maintained as the network grows.

An automated process will be introduced for current Publishers to the WordPress Repository to signal to FAIR they wish to move their chosen canonical Repository from WordPress.org to another location which supports the FAIR Protocol for Federation and includes the necessary metadata. Details will be published in due course, but the mechanism is likely to be along the lines of including of a formatted comment with a verifiable DID in the source code of a Package update. FAIR will recognize and validate the DID and other minimum requirements for Federation. The Package will automatically be re-indexing and adding to AspireCloud’s list of Federated sources. The Package will then be de-indexed from the AspirePress mirror of WordPress Packages. At the same time, the FAIR Trust Labeller will calculate the Package’s Trust Score and apply its label. The Package may then be installed from the FAIR network using its DID, and its Trust Score will begin to reflect its own Trust Signals with less reliance on its past Repository as its main Trust Signal.

## Roadmap

### Current

- Manual Federation of Trusted Repositories by invitation
- Manual Federation of Trusted Repositories from WordPress.org
- Supply Chain Threat Analysis

### First Milestone

- AspireBuild Requirements Documentation
- Implementation of security recommendations for opening Federation
- Proof-of-concept Package scanning & pass/fail validation

### Second Milestone

- Simplified Trust Scoring algorithm applied by Package Scanner
- AspireBuild[^1] Proof-of-concept
- Trust Labeller Proof-of-concept

[^1]: AspireBuild design & specification documents to be compiled separately, not related to Trust Scoring. AspireBuild will replace AspireSync to build and update a local mirror with Federated and Legacy WordPress Repository Packages, and be configurable for internal build processes, indexing of private Repositories, and feeding updates to private Aggregators. It is included here because it may have available hooks for validation of Trust Checks.

### Third Milestone

- Trust Labeller fully Federated
- Trust Scoring includes calculation details with labels

### Fourth/Future Milestone(s)

- Federation requests open to public
- Federated Trust reporting (issue logging with Trust Score adjustments)
- Appeals process available for Trust Scoring & Federation requests
- Bayesian Trust Scoring algorithm




