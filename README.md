# GraphSQL REST Demo

Minimal Spring Boot 3.5 project that exposes both REST and GraphQL endpoints, intended as a reference for integrating traditional HTTP controllers with schema-driven resolvers backed by the same service layer.

## Prerequisites
- JDK 25 (Temurin recommended)
- Maven 3.9+

## Getting Started
```bash
mvn spring-boot:run
```
The application starts on `http://localhost:8080`. Add REST controllers or GraphQL schema files under `src/main/resources/graphql` to extend the API surface.

## Build & Test
```bash
mvn clean verify
```
Runs compilation, unit tests, and integration/slice tests following the CI workflow in `.github/workflows/main.yaml`. For quick feedback loops use `mvn test`; for packaging artifacts use `mvn clean package -DskipTests`.

## Project Layout
- `src/main/java` — Application code rooted at `dev.sobue.demo`
- `src/main/resources` — Configuration (`application.yaml`), GraphQL schemas, static assets, templates
- `src/test/java` — JUnit 5 tests mirroring the main package structure
- `target/` — Build outputs (ignored in VCS)

## Contributing
Read `AGENTS.md` for repository guidelines covering structure, coding style, testing, and pull request expectations. PRs should document verification steps and link related issues when applicable.

## License
This project is distributed under the MIT License unless otherwise noted.
