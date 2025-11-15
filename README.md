# Regex Validation Testing Suite

This project helps engineers **develop, test, validate, and maintain regex patterns** used for:

- Detecting **PII leaks**  
- Catching **secrets in logs**
- Identifying **encoded or obfuscated payloads**
- Supporting **Splunk ingestion rules**
- Preventing sensitive-data exposure  

Built for developers, SecOps, detection engineers, and platform teams.

## Features

- Centralized YAML definitions  
    - All PII and sensitive-data regex patterns live in `patterns/`.
- Full automated testing  
    - Every pattern is validated against known good/bad examples.
- Works with Splunk-compatible PCRE  
    - Patterns are designed to be compatible with Splunk’s regex engine.
- Extendable  
    - Simply add new categories or patterns in `pii_patterns.yml`.
- Reduces false positives + false negatives  
    - Ensures production log pipelines don’t generate noise or miss critical leaks.
- Supports risk-based detection  
    - Use your classification (Sensitive, Confidential, Restricted, Unrestricted) to prioritize.

## Why This Exists

Regexes detecting PII/secrets are notoriously fragile.

- This suite ensures:
    - Reliability
    - Cross-team consistency
    - Safety in production
    - No accidental regression when patterns change
- It is especially useful for:
    - Observability teams
    - Logging standards committees
    - Security detection engineers
    - SREs managing ingestion pipelines

## Installation and Usage

Documentation incoming.

## Test Structure

Tests assert:

- Each valid example must match the pattern
- Each invalid example must NOT match
- Patterns produce consistent cross-language behavior (Python ↔ Splunk)

## Example Patterns Included

- SSN formats (123-45-6789, 123456789, ****6789)
- Credit cards (Visa, MC, Amex)
- Email formats
- US phone numbers
- Base64 encoded secrets
- Hex blobs
- Token/Secret/API Key indicators

## Contributions

PRs are welcome — add more patterns, test cases, documentation, or sample logs.

>[!CAUTION]
>**Security Disclaimer**: Do not commit real production log files.
>Use synthetic or redacted samples only.
