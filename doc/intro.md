# Data space Connectors
Welcome to this repository in which though several aproaches we will try to ease:
- The understanding of what a Data Space is
- The reasons why it could make sense (or not) to embrace the data space philosophy in your organization
- The importance of the connectors in a distributed data space architecture.
- The components that take part of the Fiware Data Space Connector aproach aligned with the [DSBA Technical Convergence recommendations](https://data-spaces-business-alliance.eu/wp-content/uploads/dlm_uploads/Data-Spaces-Business-Alliance-Technical-Convergence-V2.pdf)
- Which suite of components have to be deployed depending on your role/s within the data space.

## What is a Data Space
Multiple definitions can be found describing What is a Data Space is:
- "A data space is a secure and standardized digital infrastructure that enables trusted data
exchange and data-based services among various stakeholders" -[IDSA](https://docs.internationaldataspaces.org/ids-knowledgebase/v/how-to-build-data-spaces)
- "decentralized infrastructure for trustworthy data sharing and exchange in data ecosystems
based on commonly agreed principles" -[OPEN DEI initiative](https://design-principles-for-data-spaces.org/)
- "A federated, open infrastructure for sovereign data sharing based on common policies, rules, and standards." -[Gaia-X](https://gaia-x-hub.de/wp-content/uploads/2022/10/White_Paper_Definition_Dataspace_EN.pdf)

Among these definitions, the common components are that a data space is compose by different participants (organizations) that agree on common rules, standards and policies to share data and services implementing a technical solution that is accompanied by legal solutions.  
Among the multiple participants, different roles are played. The most common ones are:
- The **"data provider"**: participants that offers data and/or services
- The **"data consumer"**: After the signature of a contract, a consumer participant can access the offered data and/or services.  
- The **"marketplace"**: Data marketplaces, or data markets, are online stores that enable data sharing and collaboration. They connect data providers and data consumers, offering participants the opportunity to buy and sell data and related services in a secure environment. -[Databricks](https://www.databricks.com/glossary/data-marketplace#:~:text=Data%20marketplaces%2C%20or%20data%20markets,of%20high%20quality%20and%20consistency.)
- The **"Trust Anchor(s)"**: Ensure trust between the participants
  
## Why my organization could consider embracing a data space?
Your organization wants to offer its services / data to third parties under a set of policies for trustworthy sharing in a sovereign manner based on common policies, rules, and standards. Third parties that are not previously known and that can provide a set of verifiable credentials to perform the different workflows that are required to ingress and run the different use cases involved in a data space:
- [Onboarding of an organization in the data space](https://github.com/FIWARE/data-space-connector?tab=readme-ov-file#onboarding-of-an-organization-in-the-data-space): _Before participating in a data space, an organization needs to be onboarded at the data space's Participant List Service by registering it as trusted participant._
- [Consumer registration](https://github.com/FIWARE/data-space-connector?tab=readme-ov-file#consumer-registration): _Before being able to procure access to the provider's data service, a consumer organization needs to be registered at the provider's Trusted Issuers List as trusted issuer of VCs including claims representing a buyer of products in the provider's connector._
- [Contract management](https://github.com/FIWARE/data-space-connector?tab=readme-ov-file#contract-management): _After the registration, the consumer organization can perform contract negotiation, e.g., in order to procure access to a specific service linked to a product of the provider._
- [Service interaction](https://github.com/FIWARE/data-space-connector?tab=readme-ov-file#service-interaction): _Once the procurement has been completed, a user or an application of the consumer organization can interact with the actual service offered by the provider_

If on the other hand, your organization is sharing data/services with a known number of partners, and no plans do exist to expand them, maybe simpler data sharing mechanism could be implemented.  
## Suite of components to deploy to play different roles into a data space.
This section aims to serve as a guideline to explain at high and low levels these components to deploy a Minimum viable Dataspace in your own organization's environment, understanding the pieces that compose each component for being properly customized.
### Consumer

Both provider and consumer are required to provide verifiable credentials stating the reliability of the users acting on behalf of these organizations. Hence, an Identity and Access Management (IAM) component able to issue Verifiable Credentials (VC) is required. Currently, [Keycloak](keycloak.md) in its version 25 ([released on 240611](https://www.keycloak.org/docs/latest/release_notes/index.html#openid-for-verifiable-credential-issuance-experimental-support)) has included a new feature to manage OID4VC protocols
