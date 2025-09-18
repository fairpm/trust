# To Do:

| Document |            |
| -------- | ---------- |
| Status   | DRAFT      |
| Date     | 2025-09-17 |

## Protocol & Spec Changes & Additions

_What needs to be done to complete & refine the FAIR Trust Model_

- [ ] Add Provenance Document spec to FAIR Protocol
  - [ ] Review Prior Art, _e.g._ [in-toto Attestation Framework](https://github.com/in-toto/attestation) & [SLSA Verification Summary Attestation (VSA)](https://slsa.dev/spec/v1.2-rc1/verification_summary)
  - [ ] Define Required & Optional Content
  - [ ] Define Data Format
  - [ ] Should be signed: part of signed meta, or separate document?
- [ ] Add Install Audit Record spec to FAIR Protocol
- [ ] Determine internal checks for automation
- [ ] Determine available external validation methods
- [ ] Create weighted mathematical scoring formaula(e)
- [ ] Review suitability of Bluesky's Ozone labeller; fork & modify or greenfield project?

## Technical Architecture Requirements

_What needs to be done to fully deploy & apply the FAIR Trust Model_

- [ ] Package Validator
  - [ ] Internal checks from direct scans of Package & meta
  - [ ] External validation methodd
  - [ ] Calculate Trust Score & report to Trust Labeller (authenticated API)
  - [ ] API endpoint response to requests for updated Trust Score by DID (authenticated API)
- [ ] FAIR Trust Labeller
  - [ ] API endpoint to serve Trust Labels by DID
  - [ ] Admin panel for managing manual label application
  - [ ] Admin panel for managing third-party trust reports & appeals
- [ ] Operational Requirements
  - [ ] Trust Labelling Team
  - [ ] Manual review & label process for public Repositories & Aggregators
- [ ] FAIR (Tech Independence) Plugin
  - [ ] UI changes to support label display
  - [ ] configurable blocking by label
- [ ] Mini-FAIR Repo Plugin
  - [ ] Create & serve Provenance Document
- [ ] AspireCloud
  - [ ] Cache & report labels for packages
- [ ] AspireBuild
  - [ ] Generate Provenance Document for WordPress packages in repo mirror
  - [ ] Generate FAIR-formatted Package meta for WordPress packages in repo mirror


