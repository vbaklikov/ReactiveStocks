# REST vs gRPC

* Status: accepted
* Date: 2022-06-12

## Context and Problem Statement

For our FHIR API implementation, we would like to pick an architectural style - REST or gRPC?

## Considered Options

* REST
* gRPC

## Decision Outcome

Chosen option: "REST", because Although HL7 FHIR does mandate that the standard is implemented specifically on REST, most implementations of FHIR API are RESTful services. Moreover, some constraints and enhancements are specified as RESTful endpoints. Besides, most Open Source projects are REST implementations. For these reasons, we settle on REST for implementation.
