# Threat Index for FAIR Supply Chain

| Document |                  |
| -------- | -----------------|
| Purpose  | Working Document |
| Status   | Draft            |


## Simple List of Threats

| Threat                                   | Severity & Likelihood | Target or  Vector   | Safeguard           | Solution?       | Discussion/Issue |
| ---------------------------------------- | --------------------- | ------------------- | ------------------- | --------------- | ---------------- |
| Modification of Package in transit       | High,                 | any node in transit | Security: Technical | Package Signing | [Issue #42](https://github.com/fairpm/fair-protocol/issues/42)
| Modification of Package Meta             | Medium, Low           | Repo or Aggregator  | Security: Technical | Options         | [Issue #4](https://github.com/fairpm/fair-protocol/issues/4)
| Provenance: Licensing (Allow to Publish) | Medium, High          | Author/Publisher    | Trust               | Human Review    | [Issue #43](https://github.com/fairpm/fair-protocol/issues/43), [Issue #45](https://github.com/fairpm/fair-protocol/issues/45)
| Provenance: Technical (Correct Source)   | High, Medium          | Package             | Security: Technical | DID Resolution  | -
| Provenance: Author/Publisher Identity    | High, High            | Author/Pub + Repo   | Trust               | No              | 


