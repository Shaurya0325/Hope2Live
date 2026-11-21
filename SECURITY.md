# Security Policy

## Supported Scope

Security reports are welcome for the Hope2Live application, Supabase integration, database migrations, authentication workflows, private chat, and location or profile data handling.

## Reporting a Vulnerability

Do not disclose suspected vulnerabilities through public issues.

Send a private security report to the repository owner through GitHub:

- Open the repository's Security tab.
- Select **Report a vulnerability** when private vulnerability reporting is available.
- Alternatively, contact the repository owner privately through their GitHub profile.

Include:

- Affected component or route
- Reproduction steps
- Impact assessment
- Relevant logs or screenshots
- Suggested remediation, if available

Remove credentials and personal or medical data from all report material.

## Security Priorities

The project must protect:

- Supabase credentials and service-role keys
- Authentication sessions
- Private conversations
- Donor location and blood-report data
- Request cancellation and donation acceptance workflows
- Row Level Security and RPC authorization boundaries

## Disclosure

Please allow reasonable time for investigation and remediation before public disclosure. Security fixes may require a coordinated database migration or credential rotation.
