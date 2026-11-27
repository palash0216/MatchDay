# 1. Use C++ and Drogon for the backend

Status: Accepted
Date: 2026-11-27

## Context
Matchday is a web application for managing amateur football clubs and leagues,
including a Monte Carlo season simulator that runs ~100,000 simulated seasons
per request. The project must use only free tools, serves as a learning and
portfolio project, and builds on existing C++ experience. The simulator is
CPU-heavy and benefits from native performance and multithreading.

## Options considered
- **Java + Spring Boot** — most common backend stack in German job ads, large
  ecosystem (Spring Security, JPA, Flyway). However, it hides much of the
  underlying mechanics and does not build on existing C++ skills.
- **C++ + Crow** — lightweight and easy to start with, but less complete and
  less production-oriented (no built-in async database client).
- **C++ + Drogon** — high-performance, asynchronous framework with routing,
  middleware and a built-in PostgreSQL client. Steeper learning curve and a
  smaller community than Spring.

## Decision
We use C++20 with the Drogon framework for the backend, built with CMake and
vcpkg.

## Consequences
- ✅ Native performance for the season simulator, including multithreading.
- ✅ Deeper understanding of backend internals (migrations, auth, HTTP),
  since these are built rather than provided by a framework.
- ✅ Strong fit for C++-focused roles (automotive, embedded, industrial).
- ❌ More code written by hand; slower progress (estimated 14–16 weeks).
- ❌ Smaller ecosystem and fewer learning resources than Spring Boot.
- ❌ Weaker signal for Java/.NET-focused enterprise backend roles.