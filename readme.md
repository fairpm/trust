# FAIR Trust Working Group

## Trust Signals for FAIR

The purpose of the Trust Working Group is to establish a system of trust labels and apply them to the various entities and packages in the FAIR ecosystem via a labelling system which will be required for all FAIR-Federated network nodes ("nodes" referring to anything connected, whether a Repository, Aggrigator, or Client).

The Trust WG is broadly responsible for refining and implementing [Moderation in the FAIR Ecosystem](https://github.com/fairpm/fair-protocol/tree/main/docs/moderation), and will help build upon the work of the [CVE Labeller](https://github.com/fairpm/cve-labeller) and [Policy Engine](https://github.com/fairpm/fair-policy-engine) which were produced as proofs-of-concept at the CloudFest USA Hackathon in November 2025. Much of the tooling necessary for calculating Trust Scores will come from tools in [FAIR Forge](https://github.com/fairpm/fair-forge), many of which have trust-specific requirements.

### Trust WG deliverables are:

1. Define the set of business rules needed for establishing trust in the supply chain from end-to-end.
2. Determine what levels of trust are achievable through automated means and by manual review.
3. Determine what automated means of verification are available now or have potential in the short to medium term.
4. Create a set of relevant trust signals and draft guidelines for establishing trust through the available signals, both automated and manual, and map these to specific labels to be applied.
5. Create a set of technical requirements for meeting the identified operational business rules.
6. Implement and operate the FAIR Trust labeller.

#### Status:

- **Deliverables 1, 2, & 3: Complete.** These have been used to create the initial [requirements documentation for FAIR Forge](https://github.com/fairpm/fair-forge/tree/main/toolbox).
- **Deliverable 4: Partially Complete.** Completed elements were used in the requirements documentation for FAIR Forge. What remains is an analysis of available trust signals to create an appropriate algorithm for calculating trust scores and define operational rules for their application, including which signals represent a pass/fail requirement.
- **Deliverable 5: Partially Complete.** Most of this deliverable will be resolved through the delivery of FAIR Forge. The outstanding portion of this deliverable relates to creating a functional specification for FAIR's Trust Labeller, which is not expected to match that of a standard labeller such as were devised for the proof-of-concept CVE Labeller.
- **Deliverable 6: Partially Complete.** As a proof-of-concept, the CVE Labeller and Policy Engine form the inital work on this deliverable.

#### Next Steps:

4.1. Begin work on the Trust Scoring algorithm, anticipating ongoing iterative improvements will be made to it.
4.2. Document procedures for assigning trust labels, including managing and approving requests for federation.
5.1. Work with the FAIR Forge development team to assist with defining any remaining requirements or updates.
5.2. Draft a functional specification based on work in 4.1 & 4.2 to extend the Labeller for managing Trust Score Labels.
6.1. Support further development on the Labeller & Policy Engine proofs-of-concept, which will form a foundation for the Trust Labelling system.
6.2. Begin & oversee development of the Trust Labeller, including the identified trust-specific requirements and integration with FAIR Forge tooling.


### Discussion:

#wg-trust Channel on [chat.fair.pm](https://chat.fair.pm)

