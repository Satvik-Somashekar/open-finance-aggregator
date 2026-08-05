# Open Finance Aggregator

Day 1 scaffolding for the Open Finance Aggregator backend. The Maven reactor contains four independently runnable Spring Boot services:

- `ingestion` — future AA-style financial-data ingestion boundary
- `normalization` — future schema normalization boundary
- `retrieval` — future financial-record retrieval boundary
- `rag-service` — future grounded-answer orchestration boundary

An API gateway is intentionally deferred until the services expose public APIs that need centralized routing.

## Build

Requires Java 21 and Maven 3.9+.

```bash
mvn clean install
```

## Run a service

Use a separate terminal for each service, because the default HTTP port is `8080`.

```bash
mvn -pl ingestion spring-boot:run
```

Verify it is running:

```bash
curl http://localhost:8080/actuator/health
```

Expected response:

```json
{"status":"UP"}
```
