# Which TMSIS file is first to implement

* Status: proposed
* Date: 2022-06-14

## Context and Problem Statement

CMS provided 4 types of TMSIS files with synthetic data. We would like to pick 1 file as a basis for our implementation of MVP. Which file should be the first to implement?

## Considered Options

* Provider
* Eligibility & Enrollment
* Managed Care Entity
* TPL

## Decision Outcome

Chosen option: "Provider", because Provider file 

We decided to implement Provider type given that it is the most common type of Profile across all IGs, has reported issues in DQ Atlas, and has the most fields that map to the existing profiles. We decided to map Provider to Practitioner and Organization Resource of US Core IG.

Upon receiving the Solution Challenge, Team Skyward conducted research on the test sample data that was provided with the exercise. A total of 4 different types of files were received – Provider, Eligibility & Enrolment, Managed Care, and TPL. We looked at the following sources for our research: 

- TMSIS Data Dictionary - https://www.medicaid.gov/medicaid/data-systems/macbis/transformed-medicaid-statistical-information-system-t-msis/t-msis-data-dictionary/index.html 

- DQ Atlas - https://www.medicaid.gov/dq-atlas/landing/topics/info 

- US Core IG - http://build.fhir.org/ig/HL7/US-Core/index.html 

- Argonaut Provider Directory IG - https://www.fhir.org/guides/argonaut/pd/ 

- Da Vinci Plan Net IG - https://build.fhir.org/ig/HL7/davinci-pdex-plan-net/ 

RTI - a partner on Team Skyward, helped with the selection:

The provider file has only recently been made available to the public with the first release occurring in June 2021. Data from the file is valuable to end users and researchers. Since its release, RTI has analyzed the data for multiple projects.

A primary challenge of the file for end users is concerns with or questions about the accuracy, completeness, and inconsistent usage of provider data by states including the lack of public information from CMS on the quality of the data.

- For example, the DQ Atlas does not contain any assessments of data elements from the provider file until 2019 Release 1. For 2019, the assessments indicate that the ability to link claims to providers is generally of “low” (36 states) or “moderate” concern (9 states). These levels are generally indicative of data suitable for analysis, research, and potential decision-making. There are 6 states of “high” concern and 2 states with “unusable” data, generally making it less advisable to try to link the provider data to claims. There is little substantive change in the preliminary assessments for 2020.

- Linking providers and claims is a relatively low bar, as one might reasonably expect to be able to determine who or what entity provided a given service to a Medicaid beneficiary. It has also been a T-MSIS priority item since 2019. Ratings for the reliability of provider location information in the file are similar, with 9 states having data that are either “high” concern or unusable in preliminary 2020 files.

- It is also worth noting that in mid-2022 assessments of quality are still only available through the preliminary 2020 release of the provider data. For states and other users who do not have access to the interim data, a 2+ year lag in release of provider data and key data quality information limits the utility of T-MSIS data.

As indicated by the ratings in the CMS Data Quality Atlas, there are much more serious concerns about the quality and accuracy of provider data for other purposes, such as:

- Determining whether a provider is actively enrolled (i.e., eligible to provide services) at the time of service,

- Identifying whether a provider is affiliated with a facility, group, or individual practice,

- Classification of facilities, and

- Determination of facility characteristics such as ownership and profit status (e.g., for-profit or non-profit).

#### Opportunities and T-MSIS Priorities:

Improving the completeness and consistency of reporting of the following data classes have been a T-MSIS priority since 2020.

- National provider identifiers (NPIs),

- Types of bills,

- Provider taxonomy, and

- Facility, group and individual provider identifiers and classification.

More recent priorities have focused on ensuring that providers have only one unique identifier and that providers on claims are in the provider file as active providers at the time of service.

Selecting the **T-MSIS provider file** for the challenge is motivated by a desire to achieve the priorities noted above by making the discreet data elements more consistent and reliable for states and end users. Using a FHIR-like API enables standardized semantics and data exchange improving ease of submission, timeliness, and data quality
