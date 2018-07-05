![ga4gh logo](https://github.com/dockstore/dockstore-ui2/raw/develop/src/assets/images/sponsors/coloured/ga4gh.png)

NIH Data Commons Feedback
=======================================
This branch is specifically for collecting feedback (and suggested changes) to support the NIH Data Commons Pilot Phase.

Schemas for the GA4GH Tool Registry API
=======================================

This repository is the home for the schema for the GA4GH Tool Registry API.  The goal of the API is to provide a standardized way to describe the availability of tools and workflows.  In this way, we can have multiple repositories that share Docker-based tools and WDL/CWL-based workflows and have a consistent way to interact, search, and retrieve information from these various registries.  The end goal is to make it much easier to share scientific tools and workflows, enhancing our ability to make research reproducible, sharable, and transparent.

**[View in the Swagger Editor](https://editor2.swagger.io/#!/?import=https://raw.githubusercontent.com/ga4gh/tool-registry-schemas/develop/src/main/resources/swagger/ga4gh-tool-discovery.yaml).**  *Manually load the JSON if working from a non-develop branch version.*

The [Global Alliance for Genomics and Health](http://genomicsandhealth.org/) (GA4GH) is an international
coalition, formed to enable the sharing of genomic and clinical data.

The GA4GH [Data Working Group](http://ga4gh.org/#/) concentrates on data representation, storage,
and analysis, including working with platform development partners and
industry leaders to develop standards that will facilitate
interoperability.

Containers and Workflows Task Team
----------------------------------

The Containers & Workflows working group is an informal, multi-vendor working group born out of the BOSC 2014 codefest, consisting of various organizations and individuals that have an interest in portability of data analysis workflows. Our goal is to create specifications that enable data scientists to describe analysis tools and workflows that are powerful, easy to use, portable, and support reproducibility for a variety of problem areas including data-intensive science like bioinformatics, physics, and astronomy; and business analytics such as log analysis, data mining, and ETL.

What is the Tool Registry API Schema?
-------------------------------------

This is the home of the schema for the GA4GH Tool Registry API. The GA4GH Tool Registry API is a standard for listing and describing available tools (both stand-alone, Docker-based tools as well as workflows in CWL or WDL) in a given registry. This defines a minimal, common API describing tools that we proposal for support by multiple tool/workflow registries like [Dockstore](https://www.dockstore.org/), [BioShadock](https://docker-ui.genouest.org/app/#/), and [Agora](https://github.com/broadinstitute/agora) for the purposes of exchange, indexing, and searching.

Our current proposal is to start with a read-only API due to potentially different views and approaches to registration/security.

Key features of the current API proposal:

* read-only API
* May serve up CWl or WDL to describe a tool or represent a workflow depending on the tool/workflow submitter
* ID:  globally unique across systems and also identifies the system that it came from (ex: 123456323@agora.broadinstitute.org )

Outstanding questions:

* How do we track authorship? Should we track authorship of the tool metadata, the Docker image, or the underlying algorithm, or all of above?
* How to describe indexing and external services like an external [sparql](https://github.com/common-workflow-language/workflows#sparql) service.
* Terminology discussion (do we describe triples separately from tools? should we describe them as aggregations of tools for just the case that CWL documents have more than one tool? etc.)


How to view
------------

See the swagger editor to view our [schema in progress](http://editor.swagger.io/#/?import=https://raw.githubusercontent.com/ga4gh/tool-registry-schemas/develop/src/main/resources/swagger/ga4gh-tool-discovery.yaml).


How to contribute changes
-------------------------

Take cues for now from the [ga4gh/schemas](https://github.com/ga4gh/schemas/blob/master/CONTRIBUTING.rst) document.

At the very least, create an issue in our [Github tracker](https://github.com/ga4gh/tool-registry-schemas/issues).

Even better, fork the codebase, fix the issue, and create a pull request back to the project along with your ticket.

Adding registries
-----------------

To add a registry that supports the GA4GH Registry API:

1. fork the repo
1. modify [registry.json](registry.json)
1. submit a pull request back to the project
1. we will confirm the site is valid then accept your pull request

Cross indexing Tool Registry sites
----------------------------------

See our [registry.json](registry.json) for a list of known registries that conform to the Tool Registry API standard.

License
-------

See the [LICENSE](LICENSE)

For more information
--------------------

* http://genomicsandhealth.org/
* [INSTALL.md](INSTALL.md)
* [CONTRIBUTING.md](CONTRIBUTING.md)
* [LICENSE](LICENSE)
* [Google Groups - old](https://groups.google.com/forum/#!forum/ga4gh-dwg-containers-workflows)
* [Google Groups - new](https://groups.google.com/a/genomicsandhealth.org/forum/#!forum/ga4gh-dwg-containers-workflows)
