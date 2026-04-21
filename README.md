# Biogen (biogen)
Biogen is a global biotechnology company that discovers, develops, and delivers therapies for people living with serious neurological diseases including multiple sclerosis, Alzheimer's, and spinal muscular atrophy. Biogen operates a developer portal providing API access with interactive I/O docs, API key management, and usage reporting.

**URL:** [https://developer.biogen.com/](https://developer.biogen.com/)

## Tags:

 - Biotechnology, Healthcare, Life Sciences, Pharmaceuticals, Neurology

## Timestamps

- **Created:** 2025-01-01
- **Modified:** 2026-04-19

## APIs

### Biogen Developer API
The Biogen Developer API provides programmatic access to Biogen services including the CCS-CRX API following REST standard specifications.

**Human URL:** [https://developer.biogen.com/](https://developer.biogen.com/)

#### Tags:

 - Biotechnology, Healthcare, Life Sciences, Pharmaceuticals

#### Properties

- [Portal](https://developer.biogen.com/)
- [Documentation](https://developer.biogen.com/io-docs)
- [OpenAPI](openapi/biogen-developer-api-openapi.yml)

## Common Properties

- [Portal](https://developer.biogen.com/)
- [Website](https://www.biogen.com/)
- [Documentation](https://developer.biogen.com/io-docs)

## Features

| Name | Description |
|------|-------------|
| CCS-CRX API | Programmatic access to Copaxone CRX pharmaceutical service. |
| API Key Management | Self-service API key creation and usage monitoring via developer portal. |
| Interactive I/O Docs | Interactive API documentation for testing endpoints directly in the browser. |
| Usage Reporting | Monitor API request volumes and usage statistics per key. |
| REST Standards | REST-compliant API design following standard HTTP methods and response codes. |

## Use Cases

| Name | Description |
|------|-------------|
| Pharmaceutical Service Integration | Integrate with Biogen pharmaceutical services like CCS-CRX programmatically. |
| Developer Onboarding | Self-service API key registration and service access via developer portal. |
| Healthcare System Integration | Connect healthcare systems to Biogen services for patient program support. |

## Integrations

| Name | Description |
|------|-------------|
| Healthcare IT Systems | Connect EHR and healthcare IT systems to Biogen pharmaceutical APIs. |
| Patient Support Programs | Integrate with Biogen patient support and copay assistance programs. |

## Artifacts

### OpenAPI

- [Biogen Developer API](openapi/biogen-developer-api-openapi.yml)

### JSON Schema

- [biogen-service-schema.json](json-schema/biogen-service-schema.json)
- [biogen-api-key-schema.json](json-schema/biogen-api-key-schema.json)
- [biogen-api-key-usage-schema.json](json-schema/biogen-api-key-usage-schema.json)

## Capabilities

### Shared Per-API Definitions

- [Biogen Developer API](capabilities/shared/biogen.yaml) — 3 operations for services and API key management

### Workflow Capabilities

| Workflow | APIs Combined | Tools | Persona |
|----------|--------------|-------|---------|
| [API Access Management](capabilities/api-access-management.yaml) | Biogen | 3 | Developer |

## Vocabulary

- [Biogen Vocabulary](vocabulary/biogen-vocabulary.yaml) — Unified taxonomy mapping 2 resources, 2 actions, 1 workflow, and 1 persona

## Rules

- [Biogen Spectral Rules](rules/biogen-spectral-rules.yml) — 23 rules across 9 categories enforcing Biogen API conventions

## Maintainers

**FN:** Kin Lane

**Email:** kin@apievangelist.com
