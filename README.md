# Hope2Live

Hope2Live is a full-stack blood-donation coordination platform that connects potential blood donors with people requesting support. It combines a React interface with Supabase authentication, PostgreSQL data access, private messaging, and location-aware request matching.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![React](https://img.shields.io/badge/React-19-20232A?logo=react)](https://react.dev/)
[![Vite](https://img.shields.io/badge/Vite-8-646CFF?logo=vite&logoColor=white)](https://vite.dev/)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-3FCF8E?logo=supabase&logoColor=white)](https://supabase.com/)

## Overview

Hope2Live is designed to make blood-support coordination clearer and more organized:

- Donor profiles with blood-group and donation information
- Geographic matching for nearby blood support requests
- Request creation and donor response workflows
- Accepted-donor private chat
- Donation cooldown and eligibility-related safeguards
- Authentication and protected user dashboards
- Responsive desktop and mobile interfaces

## Safety Notice

Hope2Live is a coordination tool, not a medical decision system. Blood compatibility, donor eligibility, urgency, and transfusion decisions must always be confirmed by qualified medical professionals and emergency services.

## Technology Stack

- React 19
- Vite 8
- Supabase Auth
- Supabase PostgreSQL
- Supabase Storage
- Row Level Security
- Bootstrap 5
- Lucide React
- Custom responsive CSS

## Requirements

- Node.js 22.12 or newer
- npm
- A configured Supabase project
- Supabase schema, RPC functions, storage policies, and RLS policies required by the application

## Local Development

1. Clone the repository:

   ```bash
   git clone https://github.com/Shaurya0325/Hope2Live.git
   cd Hope2Live
   ```

2. Install dependencies:

   ```bash
   npm ci
   ```

3. Create a local environment file:

   ```bash
   cp .env.example .env.local
   ```

4. Add your Supabase project configuration:

   ```env
   VITE_SUPABASE_URL=https://your-project.supabase.co
   VITE_SUPABASE_PUBLISHABLE_KEY=your-supabase-publishable-key
   ```

5. Apply the SQL migrations in numeric order:

   ```text
   supabase/migrations/20261011000100_private_chat_and_donation_cooldown.sql
   supabase/migrations/20261011000200_require_accepted_donation_for_chat.sql
   supabase/migrations/20261011000300_current_request_chat_lifecycle.sql
   supabase/migrations/20261011000400_show_accepted_requests_to_donors.sql
   supabase/migrations/20261011000500_secure_donation_workflow.sql
   ```

6. Configure the existing RPC functions:

   - `get_matching_blood_requests`
   - `get_request_donation_responses`
   - `accept_donation_response`

7. Start the development server:

   ```bash
   npm run dev
   ```

## Quality Checks

```bash
npm run build
npm run lint
npm run preview
```

Run database authorization tests in a staging Supabase project before deployment. Verify private chat, request acceptance, cancellation, profile reports, and location visibility.

## Environment and Security

- Never commit `.env`, `.env.local`, database passwords, or Supabase service-role keys.
- Supabase publishable keys are expected to be visible in browser applications.
- Enforce authorization with Row Level Security and audited RPC permissions.
- Keep exact donor coordinates private and disclose only the location detail required for matching.
- Report vulnerabilities according to [SECURITY.md](SECURITY.md).

## Project Structure

```text
src/
  App.jsx             Application routes, dashboards, and workflows
  App.css             Responsive application styles
  main.jsx            React entry point
  lib/supabase.js     Supabase client configuration
supabase/migrations/  Database and security migrations
public/               Public assets
```

## Contributing

Contributions are welcome. Please read [CONTRIBUTING.md](CONTRIBUTING.md) and follow the [Code of Conduct](CODE_OF_CONDUCT.md).

## Security

For security concerns and responsible disclosure, see [SECURITY.md](SECURITY.md).

## License

Hope2Live is licensed under the [MIT License](LICENSE).

## Repository Status

The application requires the project's base database schema and RPC definitions to be supplied and configured separately. The repository should be tested in staging before production use, and a successful build or lint check does not replace database authorization or end-to-end testing.
