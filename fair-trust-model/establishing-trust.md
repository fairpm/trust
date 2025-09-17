# Establishing Trust Scores

> A new device or a new invention stimulates and frequently demands other new devices and inventions for its proper use.
>
> &#8212; Mervin J. Kelly, _Bell Telephone Magazine_, Summer 1953

It has always been the case that one new approach will require others in order to successfully achieve its goal. This is the case for the FAIR Protocol in seeking an improved layer of security and trust while adopting a decentralized model of Package distribution. The two objectives appear at odds, but just as the decentralization protocols and labelling systems have _open_ prior art to glean from and extend, we find the same is true for systems of establishing trust, both in Provenance for software Packages, in verifiable identity, and in the statistical analysis of the various trust factors, or Trust Signals. To achieve these ends, the FAIR Protocol will apply and extend the existing work in these areas to the new task of assigning a concretely measureable Trust Score to each Package and specific Entities in the Federated network.

In order to apply the appropriate Trust Label to Packages and Entities in the FAIR network, a range of Trust Signals are checked and monitored for changes which will trigger the recalculation of the Trust Score and any resulting update to the Trust Label applied.

## Trust Signals

Trust Signals are the various indicators and cues used to determine and apply the appropriate Trust Label to a Package or an Entity. These Trust Signals exist within the FAIR Trust Model in two overlapping forms. Some signals establish "hard" trust based upon objective factors, while others are directed toward "soft" trust based on weighted factors for more subjective evaluation of things like reputation, behaviour, or other measures which are less suited to interpretation based on a binary true/false evaluation.

The order in which the cornerstones of trust &#8212; _Security_, _Identity_, and _Best Practices_ &#8212; are listed reflect the transition from reliance on hard to soft Trust Signals. Some signals can be verified in an automated fashion with a binary yes/no answer, but may still require subjective interpretation to infer how they should affect the Trust Score.

The FAIR Trust Model includes a variety of Trust Signals which may be evaluated, many of which are optional. This approach allows Publishers to provide their choice of Trust Signal data based on what is available or easiest to provide. Some Trust Signals may contribute negatively to a Trust Score; of these, some (not all) may do so by virtue of their absence. These Trust Signals remain optional, but are deemed important enough that to affect the Trust Score if they are not provided. Trust Scores will thus be calculated with whatever Trust Signals are available, with more accurate (and likely higher) scores resulting where more Trust Signals are available for evaluation. Trust can therefore be increased through additional verifiable disclosures by the Publisher (hard trust) and through increasesing adherence to recommended or best practices (soft trust).

The Provenance Document is the first source of Trust Signals for a Package, but relevant Trust Signals will invariably extend to other (independent) sources. For example, if the DID for a Package has a domain alias (a hard signal), the domain age (soft signal) may have a bearing on the Package’s Trust Score. The absence of a valid SSL/TLS certificate or the listing of the domain in public RBLs may be negative Trust Signals, while an established history of Package releases in the Repository over time may be a positive Trust Signal.

## Trust Scores

Trust is not a binary state. The vernacular with which we speak about trust infers a progressive state, using words like establishing or building trust, which can be a complex process that follows an initial trust decision. That initial trust decision is based on a wide variety of factors, followed by an ongoing process of adjusting the amount of trust extended based upon a wider set of factors, including first-hand experience over time.

Within the FAIR network, trust must be established and maintained in many areas. This range of areas requiring certain kinds of verifiable trust poses a difficulty, as a simple yes/no is too limiting as a Trust Score. In determining that some Trust Signals will be requited while others will be optional, we create the need to offer a more complex interpretation of where Trust is calculated on a continuum. For example, five Packages may appear to return similar results from the available Trust Signals, but be awarded very different Trust Scores based on the interpretation of the available data.

These five examples may tell very different stories:

| Package   | Required | Optional Provided & Passed/Failed |
| --------- | -------- | --------------------------------- |
| One       |   8/8    |           14/30, 9/5              |
| Two       |   8/8    |           23/30, 9/14             |
| Three     |   8/8    |           23/30, 12/11            |
| Four      |   8/8    |           2/30, 2/0               |
| Five      |   6/8    |           26/30, 22/4             |

  - Package One provides 14 of 30 optional Trust Signals, of which 9 are positive and 5 are negative.
  - Package Two provides more Trust Signals, but the additional ones provided are negative with the same number passing as Package One.
  - Package Three provides the same number of Trust Signals as Package Two and has more positive scores but a lower positive:negative ratio from those than does Package One.
  - Package Four provides very little optional Trust Signals, but those few are positive.
  - Package Five provides the most optional Trust Signals with the highest number of positive results, but fails two of the required Trust Signal checks.

The challenge is to determine which of these Packages should have the highest Trust Score, and where the threshold is for a Package to be "trusted" or not, given that the score may be a sliding scale rather than an absolute number due to the inclusion of optional Trust Signals. The FAIR Trust Model will use a mathematical calculation to determine a numerical score based on the available Trust Signals, allowing for some of those signals to be weighted, and for the final score to reflect, to some extent, the amount of confidence in the score.

This approach is not at all dissimilar to the use of [Bayesian statistical analysis](https://en.wikipedia.org/wiki/Bayesian_statistics) in [spam filtering](https://en.wikipedia.org/wiki/Naive_Bayes_classifier#Spam_filtering), and is well-suited to the introduction of machine learning to improve its accuracy over time.

## Trust Labels 

From a numerical Trust Score, the FAIR Labeller may apply the appropriate Trust Label, which may be purely numerical or may be numerical with an indication of recommended Trust Thresholds which have been achieved. In some cases, a string (i.e., text) value may be presented instead of the numeric value, particularly in cases where the appropriate label represents particular states such as "Defederated" or "Known Security Risk". The FAIR Trust Labeller will make users _aware_ of the Trust Label applied to each Package and make information readily available to explain how the Trust Score was calculated and which Trust Signals were used to do so. The actual choice to install or use the package will remain with the User, who may be aware of Trust Signals which are unknown to FAIR, such as a personal connection to the Publisher or recommendation from a trusted third party.

The Trust Score applied is neither permanent nor static. Trust Signals may change, and new ones may become available or cease to be available, and the FAIR Trust Labeller will periodically recalculate Trust Scores and update Trust Labels as appropriate. Over time, Trust Signals within the FAIR network can be augmented to include telemetry and user reports, allowing reputation history to be compiled.

### Label Terminology

To simplify the trust message to Users, labels should include text and not be numerical only. This will mean setting a range where the numerical score is translated into brief but meaningful text. The terminology for applying text labels will attempt to avoid implying an "absolute" value except where scores are at extreme ends of the possible values, or where a specific label is applied to override the Trust Score -based label based on a certain condition. Provisionally, the labels applied to Packages might be along these lines:

| Range    | Label          | Indicates                                    |
| -------- | -------------- | -------------------------------------------- |
| 98-100%  | Safe           | Very high trust score AND certified trusted by a third-party (e.g., Patchstack) |
| 80-100%  | Highly Trusted | Trust Score in the top quintile              |
| 60-79%   | Trusted        | Trust Score in the fourth quintile           |
| 40-59%   | Basic Trust    | Trust Score in the third quintile            |
| 20-39%   | Untrusted      | Trust Score in the second quintile           |
| 0-19%    | Unsafe         | Trust Score in the bottom quintile           |
| 20-80%   | Partial Trust  | Package Scores in second to fourth quintile, but an Entity in the supply chain is Untrusted |
| No Score | Unknown        | Not enough data to calculate Trust Score     |
| No Score | Commercial     | Commercial Package not available for scoring |
| (Manual) | Known Unsafe   | Package has a known vulnerability            |
| (Manual) | Malicious      | Package is known to have a malicious payload |
| (Manual) | Pending        | Package unavailable pending review by FAIR   |
| (Manual) | Defederated    | Package (or its Repository) Removed by FAIR  |
| (Manual) | Closed         | Package removed by Publisher                 |

_Percentages are shown for convenience, and ranges are only samples; actual values to be determined._

An "Unknown" package would not normally be available, but could exist within a private network or closed system. A label of "Pending" might be applied by FAIR when a Package or author is undergoing review for Code of Conduct or guideline violations or other serious complaints while the matter is under review.

Labels must be accessible, with text being the primary indicator. Colours are shown in the example below as a (possible) enhanced view. A user should be able to click on the label to obtain the actual numerical score and how it was calculated, or the reason a particular label may have been applied to override the Trust Score Label.

![trust-label-display inkscape](https://github.com/user-attachments/assets/25c5f796-b5f8-4878-b212-516026cbe0e6)

### Automated Blocking & Allow-Unsafe

The FAIR Independence Client/Installer Plugin could be configured to block Package installations based on preset conditions or thresholds. For example, certain labels might require the user to re-enter their admin password or verify using an MFA token. Alternatively, Packages below a threshold or having certain labels may simply be blocked by default, or enabled through a constant in wp-config. It is noted that valid use cases exist for certain users to install an untrusted or even malicious Package.

## Trust Scoring for Specified Entities

In addition to Trust Scores for Packages, Trust Scores will be calculated and applied to key entities in the FAIR network. Trust Scores for some Entities may or may not reflect upon associated Packages. In some cases for example, the Trust Labeller would be able to indicate that while a Package may have a high Trust Score, it is hosted by a Repository with a low Trust Score.

Entities for which Trust Scores will be calculated include specific types of Nodes within the network and in some cases, may include Publishers or individual Authors and Contributors.

### FAIR Network Nodes

#### Repositories

Repositories which accept Packages from multiple Publishers to be hosted and distributed on the FAIR network must follow certain guidelines as outlined in the FAIR Protocol. As part of their acceptance for Federation, a Trust Score is assigned.

#### Mini-Repos

An Author-Publisher may decide to host their own Repository using a platform like the Mini-FAIR Repo Plugin and their choice of hosted Git repository. When a Federated Repository of this type hosts only a single Package or a small number of Packages from the same Publisher or Author, the Repository may be assigned a score based mainly upon the Publisher and the Packages it hosts, rather than upon the same Trust Signals required of other Repositories which accept public submissions. In these cases, the Trust Scores may be expected to be highly aligned, since share Provenance.

**Note:** In the early stages of Federation, FAIR expects these "Mini-Repos" to be the primary means of distributing Packages, and will begin adding them by invitation only.

#### Mirrors

Initially, mirrors within FAIR will not have Trust Scores specifically calculated. It is anticipated that requirements for mirroring Packages will focus on mirroring the WordPress.org Repository, which is done by FAIR through the AspirePress mirror indexed by AspireCloud to provide a reliable publicly-accessible mirror. This mirror is initially treated as a special case in achieving technical independence, with specific practices for both its trust and its security. If or when other public mirrors are to be Federated, they will require Trust Scores to be calculated based on Trust Signals common to other types of Node as well as mirror-specific Trust Signals to be determined.

Private mirrors have already been and may be deployed within a closed network, such as the case where a host maintains its own mirror for efficiency or other reasons. In these situations, the mirror can be assumed to inherit trust from and within the private or closed network in which it operates. Similarly, an enterprise WordPress deployment may specify pushing software updates through its own CI/CD pipeline, which may employ a mirror of selected Packages for its own purposes, and may include custom-developed Packages unique to its deployment (i.e., from a private Repository). These mirrors and any custom-developed Packages they host will not have Trust Scores calculated nor given FAIR-assigned Trust Labels.

A cache is not considered a mirror, but may be employed by a Repository or Aggregator which is already being assigned a Trust Score. If the cache is private or internal to a network, a Trust Score is not calculated, as the cache exists within a closed system. Similarly, a CDN is not assigned a separate Trust Score. For example, the AspirePress mirror uses Fastly CDN, which is a well-known, trusted and accountable third party Entity for this function.

#### Aggregators

Trust Scores for aggregators are calculated using Trust Signals common to other types of Node as well as Trust Signals specific to the Aggregator’s function, including requirements for operating an Aggregator as outlined in the FAIR protocol.

### Third-Party Labellers

Labelling services offered by third parties may or may not have Trust Scores assigned based on Trust Signals common to other types of Node, as well as Trust Signals specific to the function of a Labelling service which are yet to be determined. It is expected that most Labellers providing optional labels will be subscribed to based on known reputation, which heavily influence its Trust Score. For example, a malware scanning or security service within the ecosystem could decide to provide labels for packages based on its own security reviews or malware scans. A Trust Score can be determined in the same way as for other Nodes, but most Labellers of this type will rely on existing user or customer relationships and the reputation of its brand.

### Other Entities

#### Publishers

In the FAIR Trust Model, a Publisher holds the copyright for the Package, or a valid license permitting its distribution. The Publisher may also be an Author, or may be an Entity such as a corporation or other organization. If the Publisher is an individual and sole Author, the dual role is recognized by preserving both titles.

Not all Publishers will be assigned a Trust Score separately from the Package they publish, but those who publish many packages (whether by the same or different Authors) may be assigned a Trust Score based upon a specific set of Trust Signals. An example case might be the Publisher of a group of plugins or themes, with or without a financial transaction for the use of the Package. In such cases, a Publisher with numerous Packages having high trust scores may benefit from a simplified approval process for a new Package release based upon its track record with other Packages and its own Trust Score.

#### Authors & Contributors

In the FAIR Trust Model, Authors and Contributors are effectively synonymous terms representing the developer(s) of a Package. Within the FAIR Trust Model, if the Package includes third-party software libraries, the third-party Authors and Publishers are not directly included in an assigned Trust Score for the Package or its Authors. Authors and Contributors will have or build reputation within the ecosystem, but this is not measured (or measurable) as a Trust Score in the near to medium term. On the other hand, Authors and Contributors with verified identities may influence the Trust Score for a Package.

#### Validators

Bluesky’s trust system, from which much of the FAIR Labelling architecture is derived, includes the ability for some accounts to be trusted to verify others, much like an endorsement. These actions may be seen as a Trust Signal where one individual lends credence to another on the basis of their own reputation. While this concept would be similarly achievable within the FAIR network, it will not form an early part of the Trust Model, pending a more complete set of specifications to address this type of Entity or function. Until then, this function would be served through the mechanism of operating a third-party Labeller.





