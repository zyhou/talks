# 1. Manage AFED Documentation with ADRs

Date: 2020-01-13

Deciders: Maxime, François, Lucas, Alexis

Pull Request: [#318](https://github.com/....)

## Status

2020-01-14 accepted

## Context and Problem Statement

We find it difficult to maintain overall documentation on ARTE projects. On AFED, we decided to document the code with [JSDoc](https://jsdoc.app/) and tests. But we keep only a few traces of architecture decisions.

During the teasers migration phase from OPA to AFED, we make several decisions informally during the daily meetings. We need to find a way to keep track of these decisions.

## Considered Options

-   Using the [ARTE wiki](https://.....)
-   Setting up a real documentation of the project, for example with a [docusaurus](https://docusaurus.io/)
-   Using [ADRs](https://adr.github.io/)

## Decision Outcome

Chosen option: "Using ADRs", because it seems to be the fastest maintainable solution. ADRs can follow the Pull Request rythme.

### Positive Consequences

-   A follow-up of the architectural decisions taken on the project
-   The ADR format is light and corresponds to our development methods.
-   The structure of the ADRs is comprehensible and facilitates use and maintenance.
-   The ADR project is well maintained.

### Negative Consequences

-   A bit of extra work for the developers who will have to take some time to write the ADRs.

## Links

-   [Architecture et documentation : les ADRs](https://blog.xebia.fr/2019/03/05/architecture-et-documentation-les-adrs/)
-   [Architectural Decision Records](https://adr.github.io/)
-   [Markdown Architectural Decision Records](https://adr.github.io/madr/)
