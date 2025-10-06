# Repository Guidelines

## Project Structure & Module Organization
Source lives in `src/main/java/dev/sobue/demo`, anchored by `GraphsqlRestDemoApplication.java`. Shared configuration and GraphQL assets belong in `src/main/resources` (`application.yaml`, `/graphql`, `/templates`, `/static`). Integration and slice tests sit under `src/test/java/dev/sobue/demo`; mirror the main package layout when adding features to keep Spring scanning predictable. Generated artifacts land in `target/` and should stay out of version control.

## Build, Test, and Development Commands
Use `mvn clean verify` for a full CI-equivalent build (runs compilation, tests, and plugin checks). `mvn spring-boot:run` launches the REST + GraphQL service locally at `http://localhost:8080`. During rapid iterations, `mvn test` runs the unit and GraphQL slice suites, while `mvn clean package -DskipTests` produces an executable JAR for deployment handoffs.

## Coding Style & Naming Conventions
Code against Java 25 with Spring Boot 3.5 defaults and MapStruct/Lombok enabled; ensure annotation processing is active in your IDE. Follow 4-space indentation, braces on the same line, and prefer descriptive PascalCase class names, camelCase methods and fields, and kebab-case for resource files. Controller, mapper, and record classes should live close to their domain packages to stay aligned with Spring’s component scan. Check imports before committing—IDE auto-organize is acceptable.

## Testing Guidelines
Spring Boot configures JUnit 5 and `spring-graphql-test`; keep new tests under `src/test/java/dev/sobue/demo/...` pairing each feature package with matching tests. Name test classes `<Type>Tests` and individual methods in `shouldDoThing_whenCondition()` form. Aim to cover controller mappings, GraphQL resolvers, and mapping logic. Run `mvn test` locally before pushing, and prefer `mvn clean verify` prior to tagging releases or opening PRs.

## Commit & Pull Request Guidelines
Write commits in the imperative mood (`Add GraphQL resolver`) and scope them narrowly. Reference GitHub issues with `Fixes #123` when applicable. Before submitting a PR, confirm `mvn clean verify` passes and note any configuration steps in the description. PRs should include: purpose summary, testing evidence (command + result), screenshots for UI/static asset changes, and mention of follow-up work or known limitations.
