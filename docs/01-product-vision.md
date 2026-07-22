# Product Vision

**Version:** 0.1.0

---

# Introduction

Public data is one of the most valuable resources for scientific research, public policy evaluation, business intelligence, journalism, and evidence-based decision making.

Brazil produces a vast amount of official data through institutions such as IBGE, the Central Bank of Brazil, DATASUS, IPEA, and many other public organizations. However, despite being publicly available, these datasets remain difficult to discover, understand, and analyze.

Most users must navigate complex government portals, understand technical classifications, identify dataset and variable codes, build API queries, and manually process data before meaningful analysis can begin.

This project aims to remove these barriers by providing an open-source platform that transforms official public data into accessible knowledge through transparency, scientific rigor, and reproducible methodologies.

---

# Why This Project Exists

Public data should empower people, not overwhelm them.

Official datasets are created to inform society, yet they often require specialized technical knowledge to access and interpret. As a result, valuable information remains inaccessible to many students, researchers, journalists, public administrators, and citizens.

This project exists to bridge that gap by making official public data easier to explore without sacrificing accuracy, transparency, or scientific integrity.

---

# Problem Statement

Although Brazilian public datasets are openly available, using them efficiently remains a complex task.

Common challenges include:

* Finding the correct dataset.
* Understanding technical classifications such as CNAE.
* Identifying the appropriate variables and indicators.
* Building API queries.
* Cleaning and transforming raw data.
* Producing visualizations.
* Reproducing previous analyses.
* Understanding the methodology behind data groupings.

These difficulties create unnecessary barriers between people and the knowledge contained within public data.

---

# Proposed Solution

The platform provides an abstraction layer over official Brazilian public datasets.

Instead of requiring users to understand dataset identifiers, variable codes, or technical classifications, the platform allows exploration through intuitive concepts such as themes, indicators, regions, and time periods.

For example, instead of searching for a specific CNAE code, users simply explore themes such as:

* Technology
* Healthcare
* Education
* Agriculture
* Industry
* Commerce

The platform is responsible for translating these concepts into the technical mappings required to retrieve official data.

As the project evolves, a single theme may combine indicators from multiple official data providers while maintaining a consistent user experience.

---

# Mission

Transform official public data into accessible knowledge through transparency, scientific rigor, and reproducible methodologies.

---

# Vision

Build the reference open-source platform for exploring Brazilian public data, establishing principles and methodologies that can inspire similar initiatives worldwide.

---

# Core Principles

## User First

Users should interact with concepts rather than technical identifiers.

---

## Scientific Rigor

Every transformation, aggregation, and visualization must be supported by documented methodologies.

---

## Transparency

Every indicator must clearly identify its official source, methodology, and update date.

---

## Reproducibility

Every analysis should be reproducible using the same official data and documented methodology.

---

## Academic Methodologies

Data transformations and thematic groupings must be based on documented criteria, official references, or recognized academic methodologies.

Whenever multiple methodologies exist for representing the same concept, the platform should document each approach and preserve complete traceability.

---

## Open by Default

Methodologies, mappings, documentation, and grouping criteria should be publicly available and open to community review.

---

## Provider Agnostic

The architecture should support multiple public data providers without changing the user experience.

---

# Target Audience

The platform is designed for anyone who needs reliable public data without requiring deep technical knowledge of government databases.

Primary users include:

* Students
* Researchers
* Teachers
* Journalists
* Economists
* Public administrators
* Data analysts
* Non-profit organizations
* Companies
* Citizens interested in public information

---

# Minimum Viable Product (MVP)

The initial release focuses exclusively on the IBGE CEMPRE dataset.

The MVP will include thematic exploration through predefined categories such as Technology, Industry, Agriculture, Commerce, Healthcare, and Education.

Users will be able to explore indicators including:

* Number of companies
* Number of local units
* Total employed personnel
* Average monthly salary
* Total payroll

Visualizations will include:

* Time series
* Interactive maps
* Rankings
* Tables
* Statistical summaries

Every visualization must clearly display:

* Official data source
* Methodology used
* Time period
* Methodology version

---

# Out of Scope

The initial release does not aim to:

* Replace official government portals.
* Perform predictive analytics.
* Modify official datasets.
* Include proprietary data.
* Support every Brazilian public dataset.

These capabilities may be introduced in future releases.

---

# Long-Term Vision

The platform is designed to become a unified gateway to Brazilian public data.

Future versions may integrate providers such as:

* IBGE
* Central Bank of Brazil
* DATASUS
* IPEA
* INMET
* TSE

Rather than exposing the complexity of each provider, the platform will provide a consistent experience where users explore knowledge instead of technical systems.

---

# Project Philosophy

The project is built upon a simple idea:

> **Public data should be explored through knowledge, not technical codes.**

Every architectural decision, methodology, and interface should reduce the distance between official data and the people who depend on it.

More than providing charts or dashboards, the platform seeks to build a trustworthy knowledge layer over Brazilian public data, preserving transparency, reproducibility, and scientific integrity.
