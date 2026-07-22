# Initial Architecture

**Version:** 0.1.0
**Status:** Initial proposal

---

# 1. Purpose

This document defines the initial software architecture of the Public Data Atlas.

It describes how the concepts presented in the Product Vision, Domain Model, and Methodology Principles will be implemented from a technical perspective.

The architecture is intentionally simple, modular, and technology-independent whenever possible. It prioritizes maintainability, clarity, and long-term evolution over premature optimization.

---

# 2. Architectural Goals

The architecture has the following primary goals:

* Keep the system simple during its initial development.
* Separate business concepts from infrastructure concerns.
* Isolate external data providers from the core domain.
* Support reproducible and traceable data processing.
* Enable independent evolution of the frontend, backend, and ETL components.
* Allow future scalability without requiring a complete redesign.

---

# 3. Architectural Style

The Public Data Atlas adopts a **Modular Monolith** architecture.

The application is developed as a single deployable backend application whose internal structure is divided into independent domain modules.

This approach was selected because:

* the project is still in its early stages;
* a single deployment simplifies development;
* debugging is easier;
* deployment is straightforward;
* domain boundaries can be established before introducing distributed systems.

The project intentionally avoids microservices until real scalability requirements emerge.

---

# 4. High-Level Architecture

```text
                    +----------------------+
                    |      Frontend        |
                    |      Next.js         |
                    +----------+-----------+
                               |
                               | HTTP / REST
                               |
                    +----------v-----------+
                    |   Backend API        |
                    |   Spring Boot        |
                    +----------+-----------+
                               |
                      PostgreSQL Database
                               ^
                               |
                     Python ETL Services
                               |
          +--------------------+--------------------+
          |                    |                    |
         IBGE              DATASUS             Central Bank
```

The ETL layer is responsible for collecting and preparing official data.

The backend is responsible for domain logic and public APIs.

The frontend is responsible for user interaction.

---

# 5. Main Components

## 5.1 Frontend

The frontend provides the user interface.

Responsibilities include:

* navigation;
* filtering;
* visualization;
* user interaction;
* displaying methodology and source information.

The frontend communicates exclusively with the backend through HTTP APIs.

It never accesses the database directly.

---

## 5.2 Backend

The backend contains the project's business rules.

Responsibilities include:

* exposing REST APIs;
* validating requests;
* implementing domain rules;
* connecting domain concepts;
* enforcing methodology requirements;
* serving processed data.

The backend is implemented as a modular monolith.

---

## 5.3 ETL

The ETL layer is responsible for data ingestion.

Responsibilities include:

* retrieving official datasets;
* validating downloaded data;
* cleaning inconsistent records;
* transforming provider-specific structures;
* loading processed data into the database.

Each provider should have an independent ingestion pipeline.

---

## 5.4 Database

The database stores:

* datasets;
* metadata;
* methodologies;
* technical mappings;
* observations;
* cached provider information.

The database represents the persistent state of the platform.

---

## 5.5 External Providers

External providers remain completely isolated from the domain.

Provider-specific APIs, table identifiers, variable identifiers, and classification systems must not propagate throughout the application.

Instead, these details are translated into domain concepts through technical mappings.

---

# 6. Domain Modules

The backend is divided into domain-oriented modules.

```text
backend/

catalog/
methodology/
statistics/
geography/
visualization/
shared/
```

Each module owns its own business rules and responsibilities.

Communication between modules should occur through well-defined interfaces rather than shared implementation details.

---

# 7. Data Flow

The general data flow is:

```text
Official Provider
        |
        v
Python ETL
        |
        v
PostgreSQL
        |
        v
Spring Boot API
        |
        v
Next.js Frontend
        |
        v
User
```

This separation allows each layer to evolve independently.

---

# 8. Technology Stack

| Layer            | Technology         |
| ---------------- | ------------------ |
| Frontend         | Next.js            |
| Backend          | Java + Spring Boot |
| ETL              | Python             |
| Database         | PostgreSQL         |
| Containerization | Docker             |
| Version Control  | Git + GitHub       |

Technology choices may evolve over time without changing the conceptual architecture.

---

# 9. Deployment Strategy

During the initial development, the platform will run locally using Docker Compose.

The architecture assumes a single deployment containing:

* frontend;
* backend;
* PostgreSQL database.

The ETL component may execute independently whenever data updates are required.

Cloud deployment will be considered after the MVP is completed.

---

# 10. Security Principles

The initial architecture follows basic security principles:

* validate all external inputs;
* never expose provider credentials;
* separate internal and public models;
* preserve data integrity;
* document data provenance.

Authentication and authorization are intentionally postponed until concrete user requirements exist.

---

# 11. Scalability Strategy

The architecture is intentionally simple.

Additional complexity should only be introduced when supported by measurable requirements.

Potential future improvements include:

* Redis for caching;
* asynchronous processing;
* background job scheduling;
* distributed ETL workers;
* microservices.

These technologies are intentionally excluded from the MVP.

---

# 12. Observability

The platform should provide sufficient information to diagnose failures.

The initial implementation should include:

* structured logging;
* error reporting;
* ETL execution logs;
* API request logging.

Advanced monitoring platforms are outside the scope of the initial architecture.

---

# 13. Future Evolution

The architecture should support gradual evolution.

Possible future additions include:

* GraphQL APIs;
* authentication;
* public API keys;
* scheduled ETL pipelines;
* additional data providers;
* interactive dashboards;
* advanced analytics;
* machine learning modules.

These capabilities should extend the architecture rather than replace it.

---

# 14. Architectural Decisions

The initial architecture is based on the following decisions.

## AD-001

Use a modular monolith instead of microservices.

**Reason**

The project does not yet require distributed services.

---

## AD-002

Separate ETL from the backend.

**Reason**

Data processing and business rules have different responsibilities.

---

## AD-003

Use REST APIs between frontend and backend.

**Reason**

REST is simple, mature, and sufficient for the project's initial needs.

---

## AD-004

Keep provider-specific details outside the domain.

**Reason**

The domain should remain independent from the implementation details of official data providers.

---

## AD-005

Adopt Docker for local development.

**Reason**

Docker simplifies onboarding and guarantees consistent environments.

---

# 15. Out of Scope

The following technologies are intentionally excluded from the MVP:

* microservices;
* Kubernetes;
* message brokers;
* distributed databases;
* event sourcing;
* CQRS;
* Elasticsearch;
* service mesh.

These solutions may be evaluated in future versions if justified by actual requirements.

---

# 16. Final Principle

The architecture of the Public Data Atlas should remain as simple as possible while faithfully representing the project's domain.

Complexity is not considered a feature.

Every architectural decision should improve maintainability, transparency, and long-term sustainability rather than introducing unnecessary sophistication.
