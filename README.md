# R package validation plan - custom built software

## Specification

Every functionality needs:
 - to be defined as a very briefly written high level **user requirement**
 - to be defined as a more technically written **functional specification**
 - to be technically tested and the **tests** need to be described

We define this per R function in the R package to be validated. Thus, every R function fulfills one user requirement,
has one functional specification and may have serveral tests (at least one) depending on the risk category assigned to
the functional specification.

The links between a related user requirement, functional specification and tests need to be specifically stated.

## Versioning

All user requirements, functional specifications and tests need to be compiled into individual version controlled documents (one per class) and released together with every official release of the software.

This should be parsed automatically from the GitHub API json.

## Traceability Matrix

A matrix representation of which user requirements are covered by which functional specifications and which tests.

This should be parsed automatically from the GitHub API json.

## Risk assessment

Risk categories are assessed for every functional specification individually based on the following method.

Classify: (High = 3, Medium = 2, Low = 1)  
**Severity** - How detrimental is a failure of the assessed functionality?  
**Probability** - How likely is a failure of the assessed functionality?  
**Detectability** - How quickly will a failure of the assesed functionality be detected? 

---

Assess the **Risk class** based on **probability** and **severity** in the below matrix.

**Risk class matrix**

|Probability (x)/Severity (y) | High | Medium | Low |
|-----------------------------|------|--------|-----|
| **High**                    |   3  |   3    |  2  |
| **Medium**                  |   3  |   2    |  1  |
| **Low**                     |   2  |   1    |  1  |

---

Assess the **Final risk** based on the **Risk class** and the **detectability**.

**Final risk matrix**

|Risk class (x)/Detectability (y) | High | Medium | Low |
|---------------------------------|------|--------|-----|
| **High**                        |   3  |   3    |  2  |
| **Medium**                      |   3  |   2    |  1  |
| **Low**                         |   2  |   1    |  1  |

