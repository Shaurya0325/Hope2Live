# Contributing to Hope2Live

Thank you for helping improve Hope2Live. Please keep contributions secure, accessible, and medically responsible.

## Before Contributing

- Read the repository [README](README.md).
- Review the [Code of Conduct](CODE_OF_CONDUCT.md).
- Report security vulnerabilities privately as described in [SECURITY.md](SECURITY.md).
- Do not submit credentials, private medical data, real patient records, or Supabase service-role keys.

## Development Setup

1. Fork the repository and create a focused branch.
2. Install dependencies with `npm ci`.
3. Copy `.env.example` to `.env.local` and configure a development Supabase project.
4. Run `npm run dev` for local development.

## Making Changes

- Follow the existing React and CSS conventions.
- Keep changes focused and avoid unrelated formatting changes.
- Preserve existing authentication and Row Level Security behavior.
- Add or update tests for behavior that is changed or introduced.
- Do not present the application as a medical eligibility or blood-compatibility authority.
- Protect donor location and private chat data by default.

## Validation

Before submitting a pull request, run:

```bash
npm run build
npm run lint
```

For database or authorization changes, also test the affected workflow against a staging Supabase project.

## Pull Requests

- Use a clear title and concise description.
- Explain the problem, implementation, and verification steps.
- Link related issues.
- Include screenshots or recordings for visual changes.
- Document database migrations or environment variable changes.
- Confirm that no secrets or private user data are included.

## Reporting Bugs

Use the Bug Report issue template and include:

- Reproduction steps
- Expected behavior
- Actual behavior
- Browser and operating system
- Relevant logs without credentials or personal data
