# Operational schedule

For every package release the below steps are performed in order to achieve a validation of the functionalities
within the release.

- Step 1: Specifications are implemented according to the [R package validation guideline](https://github.com/PatrickRWright/R_package_validation/blob/master/README.md#specification) using the GitHub issue tracking functionality.
  - Risk classification of functional specifications is performed accoring to the [risk assessment](https://github.com/PatrickRWright/R_package_validation/blob/master/README.md#risk-assessment) defined in the R package validation guideline.

- Step 2: Unit tests defined in the [specifications](https://github.com/PatrickRWright/R_package_validation/blob/master/README.md#specification) are implemented in R. The technical foundation is based on the standards defined by the [testthat](https://cloud.r-project.org/web/packages/testthat/index.html) framework.

- Step 3: Using the GitHub API the specifications implemented in the GitHub issue tracker are exported (i.e. `parse_issue_json_to_csv()`) to a comma-separated values (`*.csv`) file.

- Step 4: The `*.csv` file from Step 3 is processed (i.e. `prepare_validation_documents()`) into four individual markdown (`*.md`) files. There is a file for the user requirements, the functional specifications, the test descriptions and finally a file with the traceability matrix showing that every user requirement is convered by at least one functional specification and at least one test.

- Step 5: The build of the package, including the tests, is run for Linux on [Travis CI](https://travis-ci.com/) and for Windows on [AppVeyor](https://ci.appveyor.com/). Given a successful build (indicated by "Build success" or "Your build exited with 0." at the bottom of the log) the log files are to be downloaded and saved.

- Step 6: All files from Steps 3, 4, 5 and this schedule are to be added to an inst/validation/versionnumber (e.g. inst/validation/1.0.1) directory in the R package. The directory and its files should be added to the repository through a pull request which is merged by a different person than the person sending the pull request.
