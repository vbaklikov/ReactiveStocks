# Ingestion pipeline

* Status: proposed
* Date: 2022-06-16

## Context and Problem Statement

We would like to add functionality for Bulk Upload to enable the submission of RAW TMSIS provider data in order to support existing operations.

## Considered Options

* AWS Lambda + Python script
* AWS EMR + Spark job

## Decision Outcome

Chosen option: "AWS Lambda + Python script", because AWS Lambda and Python are chosen for the implementation of MVP. Given the size of data and light footprint, a decision was made to leave EMR and Spark for later implementation when size of data is significant.
