# API Security Test Matrix

| ID | Test | Expected | Actual | Result |
|---|---|---|---|---|
| API-001 | Valid login | 200 + user data | 200 | PASS |
| API-002 | Incorrect password | Authentication rejected | 403 | PASS |
| API-003 | Non-existent account | Authentication rejected without account enumeration | 403 | PASS |
| API-004 | Missing password | 400 validation error | 400 | PASS |
| API-005 | Missing email | 400 validation error | 400 | PASS |
| API-006 | Invalid email: `not-an-email` | 400 validation error | 400 | PASS |
| API-007 | Invalid email: `teststaff` | 400 validation error | 400 | PASS |
| API-008 | Password reset with existing active account | 202 | 500 — SMTP connection refused | ENVIRONMENT ISSUE |
| API-009 | Password reset with non-existent account | Generic 202 without account enumeration | 202 | PASS |
| API-010 | Password reset with missing email | 400 | 400 | PASS |
| API-011 | Password reset with malformed email | 400 | 400 | PASS |
| API-012 | Unauthenticated access to `/roles/` | Access denied | 403 | PASS |
| API-013 | Unauthenticated access to `/staff-users/` | Access denied | 403 | PASS |
| API-014 | Unauthenticated access to `/staff-users/1/` | Access denied | 403 | PASS |
| API-015 | Login with valid active test account for authenticated testing | 200 + session | 200 | PASS |
| API-016 | Authenticated access to `/staff-users/` | 200 + staff-user data | 200 | PASS |
| API-017 | GET individual staff-user endpoint | Endpoint should respond according to supported method | 405 | OBSERVATION |
| API-018 | Unauthenticated `DELETE /staff-users/` | Request rejected | 403 | PASS |
| API-019 | Authenticated access to `/roles/` | 200 + roles data | 200 | PASS |
| API-020 | Malformed JSON on login | 400 | 400 | PASS |
| API-021 | Unexpected/extra field | Request rejected | 400 | PASS |
| API-022 | Null email/password | Authentication rejected | 403 | PASS |

## Notes

API-008 returned HTTP 500 because the local SMTP service was unavailable. This was treated as an environment/reliability issue, not a confirmed security vulnerability.

API-017 returned HTTP 405 Method Not Allowed. The intended supported methods for the individual staff-user endpoint should be confirmed with the development team. No security impact was established from this observation alone.

API-018 primarily demonstrates authorization rejection of an unauthenticated DELETE request; it should not be interpreted as proof that all DELETE behaviour is correctly implemented.
