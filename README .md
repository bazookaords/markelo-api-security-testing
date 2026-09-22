# Markelo API Security Testing

Practical API security and validation testing project completed during a cybersecurity internship.

## Project Overview

This project documents authorized security and validation testing performed against the Markelo API using local/development test accounts and test data.

The objective was to identify basic security weaknesses, validation issues, authorization problems, unexpected API behaviour, and areas requiring developer attention.

## Testing Areas

- Authentication
- Authorization
- Input validation
- Password reset functionality
- Account-enumeration resistance
- HTTP method handling
- Malformed requests
- Error handling
- Unauthenticated endpoint access

## Environment

- Django REST Framework
- PostgreSQL
- Python
- Postman
- VS Code
- Windows
- Local/development test environment

## Results

| Metric | Result |
|---|---:|
| Test cases | 22 |
| Clear passes | 20 |
| Environment issue | 1 |
| Informational observation | 1 |
| Confirmed security vulnerabilities | 0 |

### Key observations

**API-008 — Password reset SMTP failure**

A valid password-reset request returned HTTP 500 because the local SMTP service was unavailable. This was classified as an environment/reliability issue rather than a confirmed security vulnerability.

**API-017 — Individual staff-user endpoint**

A GET request to the individual staff-user endpoint returned HTTP 405 Method Not Allowed. This was recorded as an informational observation because the intended supported methods should be confirmed with the development team.

## Documentation

- [Security Testing Report](docs/Markelo-API-Security-Validation-Testing-Report.pdf)
- [Testing Methodology](docs/methodology.md)
- [Test Matrix](test-results/test-matrix.md)

## Evidence

The `evidence/` directory contains guidance for adding sanitized screenshots from the testing process.

Do not commit passwords, API tokens, session cookies, `.env` files, database credentials, production data, or confidential source code.

## Testing Approach

1. Understand the API structure.
2. Review relevant endpoint implementation.
3. Configure the local test environment.
4. Create dedicated test accounts.
5. Configure Postman.
6. Execute valid and invalid requests.
7. Compare expected and actual responses.
8. Investigate unexpected behaviour.
9. Document evidence and findings.
10. Produce the final security assessment report.

## Scope and Ethics

Testing was performed using authorized test accounts and test data in a local/development context.

This repository is a sanitized portfolio representation. It does not contain credentials, secrets, private production data, or confidential application source code.

## Author

**Daniel Opeyemi Olutoyinbo**

Cybersecurity Intern | Network & Application Security
