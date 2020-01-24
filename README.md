# R package validation plan - custom built software

## Specification

Every functionality needs:
 - to be defined as a very briefly written high level **user requirement**
 - to be defined as a more technically written **functional specification**
 - to be technically tested and the **tests** need to be described

We define this per R function in the R package to be validated. Thus, every R function fulfills one **user requirement**,
has one **functional specification** and may have serveral **tests** (at least one) depending on the risk category assigned
to the **functional specification**.

The links between a related user requirement, functional specification and tests need to be specifically stated.

## Versioning

All user requirements, functional specifications and tests need to be compiled into individual version controlled
documents (one per class) and released together with every official release of the software.

**This should be parsed automatically from the GitHub API json.**

## Traceability Matrix

A matrix representation of which user requirements are covered by which functional specifications and which tests.

**This should be parsed automatically from the GitHub API json.**

## Risk assessment

Risk is assessed for every functional specification individually based on the following method.

Classify: (:red_circle: High = 3, :large_blue_circle: Medium = 2 , :white_circle: Low = 1)  
**Severity** - How detrimental is a failure of the assessed functionality?  
**Probability** - How likely is a failure of the assessed functionality?  
**Detectability** - How quickly will a failure of the assesed functionality be detected? 

The selection of high, medium or low should be briefly explained in the **functional specification**.

---

Assess the **Risk class** based on **probability** and **severity** in the below matrix.

**Risk class matrix**

|Probability (x)/Severity (y) | High | Medium | Low |
|-----------------------------|------|--------|-----|
| **High**                    |   3 :red_circle:  |   3 :red_circle:   |  2 :large_blue_circle: |
| **Medium**                  |   3 :red_circle: |   2 :large_blue_circle:   |  1 :white_circle: |
| **Low**                     |   2 :large_blue_circle: |   1 :white_circle:   |  1 :white_circle: |

---

Assess the **Final risk** based on the **Risk class** and the **detectability**.

**Final risk matrix**

|Risk class (x)/Detectability (y) | High | Medium | Low |
|---------------------------------|------|--------|-----|
| **High**                        |   3 :red_circle: |   3 :red_circle:   |  2 :large_blue_circle: |
| **Medium**                      |   3 :red_circle: |   2 :large_blue_circle:   |  1 :white_circle: |
| **Low**                         |   2 :large_blue_circle: |   1 :white_circle:   |  1 :white_circle: |

This can be performed by using the `risk_calculator()` function in R. The source code can be found in the src
directory of this repository.

**Usage example**
```r
risk_calculator(severity = 3, probability = 1, detectability = 3)
[1] 3
```




