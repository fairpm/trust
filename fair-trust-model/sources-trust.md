# Sources of Trust Verification

In order to establish a Trust Score, a review of necessary and available Trust Signals is required, together with an evaluation of potential verification sources. As much as possible, these sources should support automated checks in order to minimize the burden of human review. For each of our cornerstones of trust, we can list potential Trust Signals.

"Always" indicates that the absence of information will impact the Trust Score.

## Security

| Trust Signal        | Required? | Scoring   | Check                             | Verification           | Goal                          |
| ------------------- | --------- | --------- | --------------------------------- | ---------------------- | ----------------------------- |
| Package Signature   | Yes       | Pass/Fail | Package Meta, Provenance Document | Verified by Installer  | authenticity & file integrity |
| Checksum            | TBD       | Pass/Fail | Package Meta, Provenance Document | Fallback for Installer | file integrity                |
| Platform Support    | Yes       | Pass/Fail | Code Scan       | Package runs on supported PHP version(s) | Avoid insecure dependencies   |
| SSL/TLS Certificate | Yes       | Pass/Fail | &#8211;                           | HTTP Headers           | security, best practice       |

## Identity

| Trust Signal        | Required? | Scoring           | Check                             | Verification           | Goal                            |
| ------------------- | --------- | ----------------- | --------------------------------- | ---------------------- | ------------------------------- |
| DID Alias           | Maybe[^1] | Maybe[^1]         | Provenance Document               | DNS Lookup             | verify source domain            |
| Contact Email       | Yes       | Pass/Fail         | Package Meta                      | Email is deliverable   | Compliance                      |
| Domain Age          | (auto)    | if provided, low weighting | Package Meta             | DNS Lookup             | Established reputation? (soft)  |
| Verifiable Identity | No        | Always            | Package Meta                      | Third-Party ID Verification[^2] | Accountability, Reputation |

[^1]: Required for certain Nodes, but not for Packages. A supplied alias must validate.
[^2]: Multiple sources exist; supported ones to be used as provided.

## Best Practices

| Trust Signal      | Required? | Scoring         | Check                             | Verification           | Goal                          |
| ----------------- | --------- | --------------- | --------------------------------- | ---------------------- | ----------------------------- |
| Security Contact  | Yes       | Pass/Fail       | Package Meta                      | Validate URI or Email  | Compliance with CRA (EU)      |
| Trademark Check   | Yes       | Pass/Fail       | WordPress plugin check tool       | &#8211;                | Avoid trademark violations    |
| SBOM              | Yes       | Pass/Fail       | Package Meta, Provenance Document | &#8211;                | Security & Compliance; avoid insecure dependencies |
| VDP               | No        | &#8211;         | Package Meta                      | TBD                    | Security practices            |
| WordPress Checks  | (auto)    | &#8211;         | WordPress code scan tool          | &#8211;                | Compliance with guidelines    |
| Support URL       | No        | Always          | Package Meta                      | URL validation         | User support mechanism        |
| License           | Yes       | Pass/Fail       | Package Meta + License file       | GPL Compatibility List | Ecosystem Compatibility       |

## Provenance

| Trust Signal      | Required? | Scoring         | Check                             | Verification           | Goal                          |
| ----------------- | --------- | --------------- | --------------------------------- | ---------------------- | ----------------------------- |



## Third-Party Identity Verification

## Reputation

## Human Review

