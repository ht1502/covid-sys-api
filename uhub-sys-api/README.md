# uhub-sys-api

This repository contains the Mule 4 application `uhub-sys-api`, an API implementation for handling COVID case reporting and lookup operations.

## Project Overview

- Mule application artifact: `uhub-sys-api-impl`
- Runtime: Mule 4.9.0
- Packaging: `mule-application`
- Primary API RAML spec: `src/main/resources/api/uhub-sys-api.raml`
- Main flows: `src/main/mule/uhub-sys-api.xml`, `src/main/mule/uhub-sys-api-2.xml`
- Implementation flows: `src/main/mule/implementation/*`
- Shared subflows: `src/main/mule/subflows/uhub-subFlow.xml`

## Features

- Register new COVID case records
- Update existing COVID case records
- Lookup COVID case by national ID
- Retrieve COVID report summaries
- Uses HTTP, DB, and secure configuration property connectors

## Build

Use Maven from the repository root:

```bash
mvn clean package
```

## Run

Deploy the generated Mule application from the `target` directory to a Mule runtime or Anypoint Runtime Fabric.

## Important Files

- `pom.xml` - Maven build and dependencies
- `mule-artifact.json` - Mule application artifact metadata
- `src/main/mule/global.xml` - global connector and configuration definitions
- `src/main/mule/global-error-handler.xml` - global error handling
- `src/main/resources/dev.yaml` / `src/main/resources/qa.yaml` - environment properties
- `src/main/resources/log4j2.xml` - logging configuration

## Notes

- The project depends on internal and MuleSoft connectors, including `ojdbc17` for Oracle database access.
- Configure environment properties and secure property placeholders before deployment.
