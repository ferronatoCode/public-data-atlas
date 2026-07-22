# Methodology Principles

**Version:** 0.1.0
**Status:** Initial proposal

---

# 1. Purpose

This document establishes the methodological principles of the Public Data Atlas.

Its purpose is to define how the project interprets, organizes, transforms, and presents official public data in a transparent, reproducible, and scientifically grounded manner.

Every classification, grouping, transformation, or derived result produced by the platform must have an explicit and documented methodological justification.

---

# 2. What Is a Methodology?

Within the Public Data Atlas, a methodology is a documented set of rules that defines how a concept is constructed from official public data.

A methodology may define:

* which datasets are used;
* which inclusion criteria are applied;
* which elements are excluded;
* which transformations are performed;
* how the resulting information should be interpreted.

A methodology is the bridge between official data and the knowledge presented to users.

---

# 3. Core Principles

## 3.1 Transparency

Every methodological decision must be documented.

Users should always be able to understand how a result was produced.

No classification or transformation should behave as a "black box."

---

## 3.2 Traceability

Every result must allow users to identify:

* the official data source;
* the methodology applied;
* the methodology version;
* the inclusion and exclusion criteria;
* the creation or revision date.

---

## 3.3 Reproducibility

Anyone should be able to reproduce the same results using:

* the same official datasets;
* the same methodology version;
* the same inclusion and exclusion criteria;
* the same transformation rules.

---

## 3.4 Scientific Rigor

Every methodology should have a documented technical foundation.

Whenever possible, methodologies should be based on:

* official documentation;
* scientific literature;
* national standards;
* internationally recognized frameworks.

When no established reference exists, the project's own methodology must be fully documented and justified.

---

## 3.5 Neutrality

The platform must not introduce political, economic, or ideological interpretations.

Its responsibility is to organize official public data consistently, allowing users to reach their own conclusions.

---

## 3.6 Clarity

Methodologies should be understandable by both researchers and non-technical users.

Whenever possible, user-facing documentation should describe concepts rather than technical codes.

---

# 4. Types of Methodologies

The Public Data Atlas recognizes different methodological origins.

## 4.1 Official Methodology

A methodology fully defined by an official institution.

Examples include methodologies published by:

* IBGE
* Central Bank of Brazil
* DATASUS
* INEP

---

## 4.2 Academic Methodology

A methodology derived from peer-reviewed research, dissertations, theses, or other recognized academic publications.

---

## 4.3 Adapted Methodology

A methodology based on an existing reference but adjusted to fit a specific dataset or analytical context.

All adaptations must be explicitly documented.

---

## 4.4 Project Methodology

A methodology created by the Public Data Atlas when no suitable reference exists.

Project methodologies must include detailed technical justification and clearly document every methodological decision.

---

# 5. Methodology Structure

Every methodology should include, at minimum:

* name;
* version;
* description;
* objective;
* author or institution;
* supporting references;
* inclusion criteria;
* exclusion criteria;
* known limitations;
* change history.

---

# 6. Inclusion and Exclusion Criteria

Every methodology must clearly define:

* what belongs to the concept being represented;
* what does not belong;
* why elements were included;
* why elements were excluded.

No technical code, category, or classification should be included without documented justification.

---

# 7. Data Transformations

Methodologies may define transformations such as:

* aggregations;
* filtering;
* normalization;
* derived calculations;
* grouping;
* standardization.

Every transformation must be documented.

Transformations must never alter the meaning of official data without explicit explanation.

---

# 8. Versioning

Methodologies are versioned.

Changes that affect the resulting data or interpretation require a new version.

Example:

```text
Technology Sector Classification

v1.0
v1.1
v2.0
```

Previously generated results must remain associated with the methodology version originally used.

---

# 9. Review Process

A methodology may have one of the following states:

* Draft
* Under Review
* Approved
* Deprecated
* Archived

Every significant modification should be recorded in the methodology's version history.

---

# 10. Limitations

Every methodology has limitations.

These limitations must be explicitly documented.

Examples include:

* incomplete data coverage;
* changes in official classifications;
* missing historical information;
* differences between data providers.

Users should always understand the scope and constraints of a methodology before interpreting its results.

---

# 11. Reproducibility Requirements

A complete methodology should answer the following questions:

* Which official datasets were used?
* Which filters were applied?
* Which technical codes were included?
* Which technical codes were excluded?
* Which methodology version generated the result?

If these questions cannot be answered, the methodology is considered incomplete.

---

# 12. Example

**Theme**

Technology

**Methodology**

Technology Sector Classification v1.0

**Methodological Foundation**

OECD recommendations adapted to the Brazilian context.

**Inclusion Criteria**

Economic activities directly related to software development, digital infrastructure, and technology services.

**Exclusion Criteria**

Activities that merely use technology as a supporting tool without producing technology-related goods or services.

**Result**

Users can clearly understand why a particular CNAE classification belongs to the Technology theme.

---

# 13. Mandatory Requirements

Every methodology must:

* have a unique identifier;
* have a version;
* include supporting references;
* document inclusion criteria;
* document exclusion criteria;
* preserve compatibility with previous versions;
* maintain a change history;
* support independent auditing.

---

# 14. Final Principle

Methodologies in the Public Data Atlas do not exist to hide decisions.

They exist to make decisions explicit.

The more transparent the path between official data and the knowledge presented to users, the more trustworthy, reproducible, and scientifically valuable the platform becomes.
