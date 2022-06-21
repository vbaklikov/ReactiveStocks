# HL7 FHIR Implementation Guide

* Status: proposed
* Date: 2022-06-14

## Context and Problem Statement

We would like to pick HL7 FHIR Implementation Guide for the basis of our implementation

## Considered Options

* US Core IG
* Argonaut Provider Directory IG
* Da Vinci Plan Net IG
* Validated Healthcare Directory Implementation Guide (VHDir IG)

## Decision Outcome

Chosen option: "US Core IG", because US Core IG is most general profile that is the basis for other implementations. For the simpliicity and speed of our implementation, we are adhering to US Core IG standard.

RTI - a partner on Team Skyward, helped with IG selection:
The pyramid diagram from the DaVinci CDex IG provides a helpful illustration of the relationship between US Core and other Implementation Guides (IGs). In the IG found at http://hl7.org/fhir/us/davinci-cdex/index.html, the Home and Background tab describe how the specifications build upon each other. ![alt text](http://hl7.org/fhir/us/davinci-cdex/profile-pyramid.svg "Figure1. Relationship of CDex to Other FHIR Standards")
“The guide is based upon the prior work from the US Core and Da Vinci Health Record Exchange (HRex) Implementation Guides. As illustrated in figure 1, this guide is built on top of FHIR and other implementation guides that provide more and more focused use cases by constraining profiles and extending functionality to cover gaps.” Using the DaVinci approach above, we believe that the Argonaut Provider Director IG is an example of an IG using the Practitioner resource that is applicable for exchange of bulk provider information. When looking at the Argonaut Provider Profile, you can see how Argonaut adapted the FHIR Practitioner resource for this use case. Another possible IG example to build on top of for a more specific T-MSIS use case is the ONC funded Validated Healthcare Directory IG. It has an overlapping use case Bulk Data IG – at the bottom of the page are links to an Overview presentation and the bulk data Zulip chat during the May 2022 Connectathon ((15353) bulk data - FHIR Community - Zulip
