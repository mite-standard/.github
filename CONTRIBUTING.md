Thank you for your interest in contributing to the MITE initiative! We welcome and appreciate all contributions.

All contributors, maintainers, and participants of the MITE initiative are expected to follow our [Code of Conduct](CODE_OF_CONDUCT.md). 

This document is organized as follows:

1. [Content Contribution](#content-contribution)
   1. [Submitting New MITE Entries](#submitting-new-mite-entries)
   2. [Editing Entries](#editing-entries)
   3. [Reviewing Entries](#reviewing-entries)
   4. [Modifications of MITE Data Standard](#modifications-of-mite-data-standard)
2. [Code Contribution](#code-contribution)
   1. [MITE Extras](#mite-extras)
   2. [MITE Web Portal](#mite-web-portal)

## Content Contribution

All content contributions should be performed using the [MITE Web application](https://mite.bioinformatics.nl/). 

### Submitting New MITE Entries

Anyone can contribute new MITE entries using the [MITE Submission Portal](https://mite.bioinformatics.nl/submission/). 
The MITE data repository aims to be a comprehensive and detailed resource on natural product-acting tailoring enzymes, and contributions from all expertise levels are welcome.
For guidance on submitting data, refer to the [MITE Tutorial](https://mite.bioinformatics.nl/tutorial), which includes a step-by-step walkthrough and an explanatory video. 
If you encounter any issues, check the [FAQ](https://mite.bioinformatics.nl/faqs) and [Troubleshooting](https://mite.bioinformatics.nl/troubleshooting) pages.
If further assistance is needed, you can reach out to a Maintainer listed in the [GOVERNANCE](GOVERNANCE.md) file. 

All new entries undergo open peer review on the [MITE Data GitHub page](https://github.com/mite-standard/mite_data/issues).

#### Attribution

All MITE entries are licensed under [CC0 "No Rights Reserved"](https://creativecommons.org/public-domain/cc0/), meaning all contributions become part of the public domain.

During data submission, you have the option to provide an [ORCID](https://orcid.org/) which will be recorded in the Changelog of the MITE entry. 
However, anonymous submissions are also welcome.

For more details, please refer to the [Terms of Use](https://mite.bioinformatics.nl/terms). 

#### Minimum MITE Requirements

To ensure high-quality data, all MITE entries must meet the following criteria:

1. Each entry must describe a single, non-redundant tailoring enzyme involved in secondary metabolite synthesis.
2. Gatekeeper enzymes (i.e., scaffold-forming enzymes) as defined by [Walsh 2023](https://doi.org/10.1039/D2NP00048B) fall outside the scope of MITE.
3. Entries must be supported by experimental data on the substrate and reaction specificity of the tailoring enzyme. Computational predictions alone are not sufficient.
4. Each entry must include at least one reaction description.

#### Bulk Contribution

If you need to submit multiple entries at once without using the MITE Submission Portal, please contact a Maintainer listed in the [GOVERNANCE](GOVERNANCE.md) file.

### Editing Entries 

Anyone can propose modifications to existing MITE entries using the "Modify entry" button on the respective entry page.
As with new submissions, you may provide an [ORCID](https://orcid.org/) for attribution.
All proposed changes undergo open peer review by voluntary experts, following the process outlined in [Submitting New MITE Entries](#submitting-new-mite-entries).

### Reviewing Entries 

All newly submitted and modified MITE entries undergo peer review before being accepted into the MITE data repository.
This review is conducted by a pool of voluntary experts who assess each entry for factual accuracy.

Reviewer membership, admittance, and responsibilities are outlined in the [Project Governance](GOVERNANCE.md) document.
Please follow the instructions outlined in this document to become a Reviewer.
Detailed information on the peer review process can be found in the [MITE Data Wiki](https://github.com/mite-standard/mite_data/wiki).

### Modifications of MITE Data Standard

The MITE Data Standard defines the structure and content of all MITE entries, ensuring consistency across the repository. 
Every entry must adhere to this standard.

The standard is implemented as a data model using the JSON Schema framework and is maintained in a dedicated GitHub repository: [MITE Schema](https://github.com/mite-standard/mite_schema).

Anyone can propose changes to the MITE Data Standard by starting a discussion on the MITE Data Standard [Discussions Board](https://github.com/orgs/mite-standard/discussions/3). 
Proposed modifications are periodically reviewed by the MITE governing body (as defined in the [Project Governance](GOVERNANCE.md)) and are approved or rejected by majority vote.

## Code Contribution

All repositories in the MITE Data Standard Organization follow the [GitHub Flow](https://guides.github.com/introduction/flow) model for code contributions.

While code contributions are welcome, please discuss your ideas first on the MITE Standard [Discussions Board](https://github.com/orgs/mite-standard/discussions) before submitting a pull request.

#### Step-by-step guide

To contribute code, follow these steps. For repository-specific details, refer to the README of the respective repository.

1. [Create a fork](https://help.github.com/articles/fork-a-repo) using your GitHub account (or an organization you belong to).
2. [Clone your fork](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository) to your local machine.
3. Install `hatch` using one of the recommended methods.
4. Install the package using `hatch env create`
5. Initialize `pre-commit` with `hatch run pre-commit install`
6. Make changes to the code
7. Test that your code passes quality assurance by running `pytest`
8. Commit changes to your fork with `git commit`. `pre-commit` will run a set of linters to ensure high code quality.
9. Push changes to your fork with `git push`
10. Repeat steps 5-8 as needed
11. Describe your changes in the `CHANGELOG.md` file
12. Submit a pull request back to the upstream repository
13. A code review takes place, resulting in accept, accept with revision, or reject. 
14. If accepted and revisions have taken place, the fork is merged into `main` and deleted.

#### Code style

- All projects use a `pyproject.toml` file for metadata management, including dependencies. Semantic versioning and keeping a CHANGELOG are mandatory.
- `pydantic` models are preferred where applicable. Static typing outside the use of `pydantic` is strongly encouraged but not enforced.
- `ruff` is used for linting and formatting (applied automatically using `pre-commit`). See the `pyproject.toml` files for a list of plugins.
- Functions, classes, and methods must have expressive documentation using `numpy`-style docstrings. In-line comments are strongly discouraged.
- Logging is performed using the built-in `logging` module.
- Unit testing is performed exclusively using the `pytest` library.
- A continuous integration service using GitHub Actions is in place that run automated checks once a pull request is submitted. 

### MITE Extras

The [MITE Web Portal Repository](https://github.com/mite-standard/mite_extras) contains the MITE data model and associated validation functionality.
To maintain the integrity of the project, all new functionality must be unit tested.

### MITE Web Portal

The [MITE Web Portal Repository](https://github.com/mite-standard/mite_web) contains the code for the MITE web application.
As a web application, unit testing is less strictly enforced. However, a local rebuild of the Docker container is required before submitting a pull request.
