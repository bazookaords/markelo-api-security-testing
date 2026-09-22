# API Security Testing Methodology

## Objective

The objective was to identify basic security weaknesses and validation issues in the Markelo API using authorized test accounts and test data.

## Testing Areas

- Authentication
- Authorization
- Input validation
- Password reset functionality
- HTTP method handling
- Unauthenticated endpoint access
- Account-enumeration resistance
- Error handling

## Testing Process

1. Understand the API structure.
2. Review relevant endpoint implementations.
3. Configure the local test environment.
4. Create dedicated test accounts.
5. Configure Postman.
6. Execute valid and invalid requests.
7. Compare expected and actual responses.
8. Investigate unexpected responses.
9. Document findings and evidence.
10. Produce the final security assessment report.

## Tools

- Postman
- Django REST Framework
- PostgreSQL
- Python
- Git
- VS Code

## Testing Principles

Testing was limited to authorized local/development resources and dedicated test accounts/test data.

The review focused on observable API behaviour and did not include unauthorized access to production systems.

## Result Classification

- **PASS:** Actual behaviour matched the expected security or validation behaviour.
- **ENVIRONMENT ISSUE:** Behaviour was affected by a local configuration or dependency issue rather than a confirmed application vulnerability.
- **OBSERVATION:** Unexpected or notable behaviour was recorded for clarification without enough evidence to classify it as a security vulnerability.
