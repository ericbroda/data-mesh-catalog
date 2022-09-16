# Data-Mesh-Catalog - Backstage loadable data product registry data

This repository contains an inventory of data that can be loaded into
a Backstage software catalog.  There are several data types loaded:
- Organizations
- Domains
- Systems
- APIs
- Data Products

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

The hierarchical representation looks like this:
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

## Data Type: Systems

## Data Type: APIs

## Data Type: Data Products

