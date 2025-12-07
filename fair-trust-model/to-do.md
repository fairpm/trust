# To Do:

| Document |            |
| -------- | ---------- |
| Status   | DRAFT      |
| Date     | 2025-12-07 |

## Protocol & Spec Changes & Additions

_What needs to be done to complete & refine the FAIR Trust Model_

- [ ] Add Provenance Document spec to FAIR Protocol
  - [x] Review Prior Art, _e.g._ [in-toto Attestation Framework](https://github.com/in-toto/attestation) & [SLSA Verification Summary Attestation (VSA)](https://slsa.dev/spec/v1.2-rc1/verification_summary)
  - [ ] Define Required & Optional Content
  - [x] Define Data Format
  - [x] Should be signed: part of signed meta, or separate document?
- [ ] Add Install Audit Record spec to FAIR Protocol
- [ ] Add SBOM (& Dependency?) spec to FAIR Protocol
- [ ] Build list of required & optional Trust Signals
  - [x] Review Prior Art, _e.g._ [Open Code Badge Program](https://badges.opencode.de/en/), [Digital ID & Authentication Council of Canada's Trust Framework](https://diacc.ca/trust-framework/)
- [x] Determine internal checks for automation
  - [x] Review [WordPress/theme-check/checks](https://github.com/WordPress/theme-check/tree/master/checks), [WordPress/plugin-check](https://github.com/WordPress/plugin-check/tree/trunk), & [WordPress plugin-check Github Action](https://github.com/WordPress/plugin-check-action) for any revisions needed for FAIR
- [x] Determine available external validation methods
- [ ] Evaluate Verifiable Identity as a strong Trust Signal (also see [Web of Trust Map](https://www.weboftrust.org/topo))
  - [ ] Services: [Identity.com](https://www.identity.com/), [EU Digital Identity Wallet](https://ec.europa.eu/digital-building-blocks/sites/spaces/EUDIGITALIDENTITYWALLET/pages/694487738/EU+Digital+Identity+Wallet+Home), [TrustGrid](https://trustgrid.com/), [Hyperledger Indy](https://www.lfdecentralizedtrust.org/projects/hyperledger-indy), [Northern Block](https://northernblock.io/)
  - [ ] Consortia: [DIACC](https://diacc.ca/) - Digital ID & Authentication Council of Canada, [TOIP](https://trustoverip.org/) - Trust Over IP, [OpenID](https://openid.net/) - Open ID for Verifiable Credentials (OID4VC), [LFDT](https://www.lfdecentralizedtrust.org/) - Linux Foundation Decentralized Trust, [EUDI Wallet Consortium](https://eudiwalletconsortium.org/), [EBSI](https://ec.europa.eu/digital-building-blocks/sites/spaces/EBSI/pages/447687044/Home) - European Blockchain Services Infrastructure, [DIF](https://identity.foundation/) - Decentralized Identity Foundation (DIF)
  - [ ] Specifications & Regulations: [Verifiable Credentials Data Model v2.0](https://www.w3.org/TR/vc-data-model/) (W3C), [The European Digital Identity Wallet Architecture and Reference Framework](https://digital-strategy.ec.europa.eu/en/library/european-digital-identity-wallet-architecture-and-reference-framework) (ARF), [AnonCreds Specification](https://hyperledger.github.io/anoncreds-spec/) (Hyperledger), [eIDAS Regulation](https://digital-strategy.ec.europa.eu/en/policies/eidas-regulation), [European Digital Identity (EUDI) Regulation](https://digital-strategy.ec.europa.eu/en/policies/eudi-regulation)  
- [ ] Create weighted mathematical scoring formaula(e)
- [x] Review suitability of Bluesky's Ozone labeller; fork & modify or greenfield project?

