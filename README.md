# R package validation plan - custom built software

## Specification

Every functionality needs:
 - to be defined as a very briefly written high level **user requirement**
 - to be defined as a more technically written **functional specification**
 - to be technically tested and the **tests** need to be described

We define this per R function in the R package to be validated. Thus, every R function fulfills one user requirement,
has one functional specification and may have serveral tests depending on the risk category assigned to
the functional specification.

The links between a related user requirement, functional specification and tests need to be specifically stated.

## Versioning

All user requirements, functional specifications and tests need to be compiled into individual version controlled documents (one per class) and released together with every official release of the software.

This should be parsed automatically from the GitHub API json.

## Traceability Matrix

A matrix representation of which user requirements are covered by which functional specifications and which tests.

This should be parsed automatically from the GitHub API json.

## Risk assessment

Risks are assessed for all functional specifications based on the following method.

Classify: (High = 3, Medium = 2, Low = 1)  
**Severity** - How detrimental is a failure of the assessed functionality?  
**Probability** - How likely is a failure of the assessed functionality?  
**Detectability** - How quickly will a failure of the assesed functionality be detected? 

| Probability  / Severity | High | Medium | Low |
|-------------------------|------|--------|-----|
| High                    |      |        |     |
| Medium                  |      |        |     |
| Low                     |      |        |     |
