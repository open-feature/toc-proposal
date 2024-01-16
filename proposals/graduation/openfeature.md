# [Project] Graduation Proposal

[OpenFeature](https://openfeature.dev) is an open specification for feature flag management, created to support a robust feature flag ecosystem using cloud-native technologies. OpenFeature provides a unified API and SDK, and a developer-first, cloud native implementation, with extensibility for open source and commercial offerings.

## Evaluation API
The Evaluation API is the primary component of OpenFeature that application authors interact with. The Evaluation API allows developers to evaluate feature flags to alter control flow and application characteristics.

## Providers
Providers are responsible for performing flag evaluations. They provide an abstraction between the underlying flag management system and the OpenFeature SDK. Providers can wrap a vendor SDK, call a bespoke flag evaluation REST API, or even parse some locally stored file to resolve flag values. This allows the underlying flag evaluation logic to be changed without requiring major code refactoring. An application integrator can register one provider at a time. Registering an additional provider will override any previously configured providers. If no provider is set, OpenFeature will no-op and return the default value passed to the Evaluation API. Providers are set through the Evaluation API. They're globally registered, and a change affects both new and existing OpenFeature clients.

## Evaluation Context
The evaluation context is a container for arbitrary contextual data that can be used as a basis for dynamic evaluation. Static data, such as the host or an identifier for the application, can be configured globally. Dynamic evaluation context, such as the IP address of the client in a web application, can be implicitly propagated or explicitly passed to during flag evaluation and can be merged with static values.

## Hooks
Hooks are a mechanism that allows for the addition of arbitrary behavior at well-defined points of the flag evaluation lifecycle. Use cases include validation of the resolved flag value, modifying or adding data to the evaluation context, logging, telemetry, and tracking.

## Events
Events enable the ability to react to state changes in the provider or underlying flag management system. These include changes in provider readiness, error status, or, perhaps most interestingly, flag configuration changes.

## FlagD
Flagd is a feature flag daemon with a Unix philosophy. Think of it as a ready-made, open source, OpenFeature compliant feature flag backend system.

OpenFeature's repositories have ~1500 GitHub stars and 248 contributors and 370+ users registered for the OpenFeature community Slack. OpenFeature was open sourced in 2021, and joined the CNCF at Sandbox level in May 2022 and then reached incubation status in December 2023. It is currently used in production at scale all around the world, by many companies including at Codecentric, Dynatrace, Ebay, Proofpoint, Schweitzer Engineering Labs, Tapico, Utility Warehouse, Virtru and many more. It is also offered as a solution by a number of Feature Flag Vendors such as Cloudbees, ConfigCat, Devcycle, Featbit, Flagsmith, Flipt, GO Feature Flag, Harness, LaunchDarkly, PostHog, Split, Unleash.

The project maintainers believe that OpenFeature meets the requirements for Graduation status.


## Graduation State Criteria
_**Project should address each graduation criteria listed below**_

### * Have committers from at least two organizations.
We have [committers](https://openfeature.devstats.cncf.io/d/5/companies-table?orgId=1&var-period_name=Last%20decade&var-metric=committers) from Cloudbees, Dynatrace, Flagsmith, Google, Independents, Microsoft and Spotify as well as many others.

### * Have achieved and maintained a [Core Infrastructure Initiative Best Practices Badge](https://bestpractices.coreinfrastructure.org/).
The OpenFeature Spec has achieved an [OpenSSF Best Practices Badge](https://www.bestpractices.dev/en/projects/6240)

### * Have completed an independent and third party security audit with results published of similar scope and quality as [this example](https://github.com/envoyproxy/envoy#security-audit) which includes all critical vulnerabilities and all critical vulnerabilities need to be addressed before graduation.

### * Explicitly define a project governance and committer process. The committer process should cover the full committer lifecycle including onboarding and offboarding or emeritus criteria. This preferably is laid out in a GOVERNANCE.md file and references an OWNERS.md file showing the current and emeritus committers.
Project governance including granting and revoking rights, expectations, and voting are outlined in [governance documents](https://github.com/open-feature/community/blob/main/governance-charter.md). All maintiners are managed with peribolos and can be found in the [configuration files](https://github.com/open-feature/community/tree/main/config/open-feature).

### * Explicitly define the criteria, process and offboarding or emeritus conditions for project maintainers; or those who may interact with the CNCF on behalf of the project. The list of maintainers should be preferably be stored in a MAINTAINERS.md file and audited at a minimum of an annual cadence.
Maintainers may be removed after 3 months of inactivity and are removed based on the process outlined in the [Contributor ladder](https://github.com/open-feature/community/blob/main/CONTRIBUTOR_LADDER.md). Those removed will be changed to emeritus in the [community-members.md](https://github.com/open-feature/community/blob/main/community-members.md)

### * Have a public list of Project adopters for at least the primary repo (e.g., ADOPTERS.md or logos on the Project website). For a specification, have a list of adopters for the implementation(s) of the spec. Refer to [FAQs](https://github.com/cncf/toc/blob/main/FAQ.md#what-is-the-definition-of-an-adopter) for guidelines on identifying adopters.
See the [Adopter.md](https://github.com/open-feature/community/blob/main/ADOPTERS.md) in the community repository.
## Incubation Details
_**Project should address each area listed below**_
OpenFeature was accepted as an [Incubation level project](https://github.com/cncf/toc/blob/main/proposals/incubation/openfeature.md) in December 2023. There are no outstanding issues raised during the incubation due diligence that remain to be addressed.
[Incubation Due Diligence Document](https://docs.google.com/document/d/1hALzMUqtMEEIXLE3eZJaa4xywnptplKUHc_X4NWAezo/edit)
