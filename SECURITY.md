# Security Policy

## Supported Versions

DUEFORCE is actively developed. Security fixes are applied to the currently deployed production version and the latest maintained source version.

## Reporting a Security Vulnerability

If you discover a security vulnerability in DUEFORCE, please report it privately to the project owner.

**Do not open a public GitHub Issue, Pull Request, or discussion for an unpatched security vulnerability.**

When reporting an issue, please include:
- A clear description of the vulnerability
- Steps to reproduce the issue
- The affected page, feature, or component
- Relevant screenshots, logs, or proof of concept
- The potential security impact

Do not include passwords, authentication tokens, Firebase service-account credentials, personal customer data, or other sensitive information in the report.

## Responsible Disclosure

Please allow reasonable time for the issue to be investigated and, where appropriate, fixed before publicly disclosing technical details.

Security researchers must not access, modify, delete, or download data belonging to other DUEFORCE users.

## Credential Security

Never commit or publish:
- Firebase Admin SDK service-account JSON files
- Private API keys or secrets
- Authentication credentials
- Database credentials
- User/customer personal data

If a secret is accidentally exposed, it should be revoked or rotated immediately.

## Scope

This policy covers the DUEFORCE website, application code, Firebase configuration/security rules, and related production services controlled by the project.

Third-party services and infrastructure are subject to their respective security policies.

## Contact

For private security reports, contact the DUEFORCE project owner through the project's maintained private contact channel.

Thank you for helping keep DUEFORCE and its users secure.
