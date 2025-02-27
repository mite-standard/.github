Contributions to the MITE initiative are welcomed and encouraged. Thanks for
considering to participate.

All contributors, maintainers, and participants of the MITE initiative are
expected to follow our [Code of Conduct](CODE_OF_CONDUCT.md). 

This document is organized as follows:

1. [Content Contribution](#content-contribution)
   1. [Submitting New MITE Entries](#submitting-new-mite-entries)
   2. [Editing Entries](#editing-entries)
   3. [Reviewing Entries](#reviewing-entries)
   4. [Modifications of MITE Data Standard](#mite-standard)
2. [Code Contribution](#code-contribution)
   1. [MITE Web Portal](#mite-web)
   2. [MITE Extras](#mite-extras)


## Content Contribution

All content contributions should be performed using the [MITE Web application](https://mite.bioinformatics.nl/). 

### Submitting New MITE Entries

MITE entries can be created by anyone, using the [MITE Submission Portal](https://mite.bioinformatics.nl/submission/). 
The MITE data repository strives to be a detailed, descriptive resource on natural product-acting tailoring enzymes,
and expertise is welcomed from anywhere. A detailed tutorial for data submission can be found at [MITE Tutorial](https://mite.bioinformatics.nl/tutorial),
including a step-by-step explanatory video. If you run into issues, please see the [FAQ](https://mite.bioinformatics.nl/faqs) and 
[Troubleshooting](https://mite.bioinformatics.nl/troubleshooting) pages, or contact one of the Maintainers specified in 
the [GOVERNANCE](GOVERNANCE.md) file. All new entries undergo open peer review on the [MITE Data GitHub page](https://github.com/mite-standard/mite_data/issues).

#### Attribution

MITE entries are licensed under [CC0 "No Rights Reserved"](https://creativecommons.org/public-domain/cc0/) and all contributions become part of the public domain.
During data submission, you may provide an [ORCID](https://orcid.org/) which is then stored in the "Changelog" of the MITE entry. 
However, anonymous submissions are also invited. For more details, see the [Terms of Use](https://mite.bioinformatics.nl/terms). 

#### Minimum MITE Requirements

1. Each MITE entry characterizes a single, non-redundant **tailoring enzyme** involved in secondary metabolite synthesis.
2. Gatekeeper enzymes (~=scaffold-forming) as defined by [Walsh 2023](https://doi.org/10.1039/D2NP00048B) are outside the scope of MITE.
3. MITE entries need to be based on experimental data on the substrate- and reaction-specificity of the tailoring reaction. Predictions solely based on computational predictions are not permitted.
4. Each MITE entry must be associated with one or more reaction descriptions.

#### Bulk Contribution

If you would like to submit many entries at once without using the MITE submission portal, please contact one of the Maintainers specified in 
the [GOVERNANCE](GOVERNANCE.md) file.

### Editing Entries 

Modifications to existing MITE entries can be proposed by anyone, using the "Modify entry" on the respective entry page.
As with newly generated entries, you may provide an ORCID for attribution of your contribution.
All proposed changes are reviewed by voluntary experts performing open peer review as described under [Submitting New MITE Entries](#submitting-new-mite-entries)

### Reviewing Entries 

All newly submitted and modified existing MITE entries are peer-reviewed before admittance to the MITE data repository. 
Peer review is performed by a pool of voluntary reviewers who scrutinize the entry for factual correctness.
Reviewer membership and conduct is described in the [Project Governance](GOVERNANCE.md).
New entries/proposed modifications may be rejected if they are outside the scope of MITE, are factual incorrect and considered "unfixable" by the Reviewers, or violate the community guidelines/code of conduct.
Submitters are invited to participate in this discussion.

### Modifications of MITE Data Standard

The MITE Data Standard regulates the data structure and content of MITE entries. All MITE entries must adhere to the MITE Data Standard.
The Data Standard is implemented as a data model using the JSON Schema framework. It is organized in its own GitHub Repository named [MITE Schema](https://github.com/mite-standard/mite_schema).
Changes to the MITE Data Standard can be proposed by anyone using the MITE Standard [Discussions Board](https://github.com/orgs/mite-standard/discussions/3).
Changes are reviewed periodically by the MITE governing body (defined in the [Project Governance](GOVERNANCE.md)) and approved or rejected by majority vote. 

## Content Contribution

All repositories in the MITE Data Standard Organization use the [GitHub Flow](https://guides.github.com/introduction/flow)
model for code contributions. In general, code contributions are welcome, but make sure to first discuss them using 
the MITE Standard [Discussions Board](https://github.com/orgs/mite-standard/discussions).

#### Step-by-step guide

In general, code contributions should follow these steps (for details, see the `README` of the individual repositories):

1. [Create a fork](https://help.github.com/articles/fork-a-repo) of the respective upstream
   repository using your GitHub account (or in one of your organizations)
2. [Clone your fork](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository)
3. Install `hatch` using one of the methods described here
4. Install the package using `hatch env crate`
4. Initialize `pre-commit` with `hatch run pre-commit install`
5. Make changes to the code
6. Test that your code passes quality assurance by running `pytest`
7. Commit changes to your fork with `git commit`. `pre-commit` will run a set of linters to ensure high code quality.
8. Push changes to your fork with `git push`
9. Repeat steps 5-8 as needed
10. Describe your changes in the `CHANGELOG.md` file
11. Submit a pull request back to the upstream repository
12. A code review takes place, resulting in accept, accept with revision, or reject. 
13. If accepted and revisions have taken place, the fork is merged into `main` and deleted.

#### Code style

- All projects use a `pyproject.toml` file for metadata management, including dependencies. Semantic versioning and keeping a CHANGELOG are mandatory.
- `pydantic` models are used where possible. Static typing outside the use of `pydantic` is strongly encouraged but not enforced.
- `ruff` is used for linting and formatting (applied automatically using `pre-commit`). See the `pyproject.toml` files for a list of plugins.
- Expressive documentation of function using `numpy`-style docstrings is mandatory. In-line comments are strongly discouraged.
- Logging is performed using the `logging` module.
- Unit testing is performed solely using the `pytest` library.
- A continuous integration service is in place that run automated checks once a pull request is issued. 

### MITE Extras

The [MITE Web Portal Repository](https://github.com/mite-standard/mite_extras) contains the MITE data model and associated validation functionality.
Given its importance for the integrity of the project, all functionality must be unit tested. 

### MITE Web Portal

The [MITE Web Portal Repository](https://github.com/mite-standard/mite_web) contains the code for the MITE web application.
Since it is a web application, unit testing is less strictly handled. However, a local rebuild of the Docker container is required before a pull request.