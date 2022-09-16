# Data-Mesh-Catalog - Backstage loadable data product registry data

This repository contains an inventory of data that can be loaded into
a Backstage software catalog.  There are several data types loaded:
- Organizations (Backstage kinds: "Group" and "User")
- Domains (Backstage kinds: "Domain")
- Systems (Backstage kinds: "System")
- APIs (Backstage kinds: "API")
- Data Products (Backstage kinds: "Component")

## Data Type: Organization

Organization data is located in the following files:
~~~~
orgs/brodagroupsoftware.yaml
~~~~

Two types of organizations exist:
- Groups, hierarchical representations of organizational units that contain users and other groups
- Users, representing people

The following Groups (identified by its name) are in the data:
- BrodaGroupSoftware, the top-level organization
- IT, a group within BrodaGroupSoftware

The following Users (identified by their name) are in the data:
- eric.broda, in group: IT
- albert.einstein, in group: IT
- isaac.newton, in group: IT
- marie.curie, in group: IT
- michael.faraday, in group: IT

A hierarchical representation looks like this:
~~~~
- BrodaGroupSoftware
  |
  +-- IT
      |
      +-- eric.broda
      +-- albert.einstein
      +-- isaac.newton
      +-- marie.curie
      +-- michael.faraday
~~~~

## Data Type: Domains

Domain data is located in the following files:
~~~~
domains/enterprise-domains.yaml
~~~~

A domain represents a group of systems.  A banking context is
used for these domains with common banking entity groups that represent domains.

The following domains (identified by their name) are in the data:
- account-domain, a domain for systems related to account
- party-domain, a domain for systems related to party
- product-domain, a domain for systems related to product
- transaction-domain, a domain for systems related to transaction

## Data Type: Systems

System data is located in the following files:
~~~~
domains/enterprise-systems.yaml
~~~~

A system represent a group of deployable set of software.  A banking context is
used for these domains with common banking applications that represent systems.

The following systems (identified by their name) are in the data:
- customer-analytics, domain: party-domain
- customer-web, domain: party-domain
- customer-advisor, domain: party-domain
- customer-mobile, domain: party-domain
- core-banking-accounts, domain: account-domain
- core-banking-products, domain: product-domain
- core-banking-transactions, domain: transaction-domain
---

A hierarchical representation (domains/systems) looks like this:
~~~~
- party-domain
  |
  +-- customer-analytics
  +-- customer-web
  +-- customer-advisor
  +-- customer-mobile

- account-domain
  |
  +-- core-banking-accounts

- product-domain
  |
  +-- core-banking-products

- transaction-domain
  |
  +-- core-banking-transactions
~~~~

## Data Type: APIs

API data is located in the following files:
~~~~
apis/petstore.yaml
~~~~

An API represent an OpenAPI specification that defines a RESTful access mechanism
to a resource.  A standalone API - Petstore API - is used to demonstrate API capabilities.

## Data Type: Data Products

Data Product data is located in the following directory:
~~~~
dataproducts
~~~~

There are several data products are available in:
- account data product (in dataproducts/account)
- party data product (in dataproducts/party)
- product data product (in dataproducts/product)
- transaction data product (in dataproducts/transaction)

A data product are defined in Zhamak Dehghani's book,
[Data Mesh: Delivering Data Driven Value](https://www.amazon.com/Data-Mesh-Delivering-Data-Driven-Value/dp/1492092398).
The key attributes of a data products for our purposes are listed below:
- bounded contexts for a set of identifiable data
- owned by a person/group
- accessed via APIs
- discoverable

There are several files that define a data product:
- catalog-info.yaml: a Backstage catalog information file that describes the data product
- specification-api.yaml: the OpenAPI specification that describes the APIs (discover, observe, etc) to access an API
- specification-event.yaml: an AsyncAPI specification that describes an subscribable data product event
- specification-license.yaml: a license that governs use of the data product
- specification-query.yaml: a list of queries supported by this data product
- specification-schema.yaml: the metadata for the data managed by the data product