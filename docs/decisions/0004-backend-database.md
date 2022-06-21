# Backend Database

* Status: accepted
* Date: 2022-06-12

## Context and Problem Statement

We would like to pick a database to store FHIR data in the backend. AWS RDS, AWS Redshift, or AWS DynamoDB?

## Considered Options

* AWS RDS
* AWS DynamoDB
* AWS Redshift

## Decision Outcome

Chosen option: "AWS RDS", because AWS Redshift is an analytical olap mpp engine that is not suited for CRUD operations. Not a good fit for this implementation.
AWS DynamoDB is an excellent choice for the backend for its scalability. Production setup should be on DynamoDB
AWS RDS is selected for this initial implementation as it is an easiest fit (RDBMS) and connects natively with HAPI API.
