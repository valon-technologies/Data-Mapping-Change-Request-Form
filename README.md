# Valon Data Mapping Change Request Form

A lightweight, fully static web app for submitting and reviewing data mapping change requests — hosted on GitHub Pages with no backend required.

## Pages

| File | Description |
|------|-------------|
| `index.html` | Change request submission form |
| `thankyou.html` | Confirmation page after submission |
| `dashboard.html` | Read-only submissions viewer |

## Features

- **Smart autocomplete** on VOS Entity/Table and Field Name fields, powered by the Valon data schema (195 entities, 2,596 fields)
- **Email confirmation** sent to the submitter via EmailJS on every submission
- **Persistent submissions dashboard** — all submissions are saved and viewable in a searchable, filterable table with click-to-expand detail view
- **Fully static** — no server, no database, works entirely on GitHub Pages

## Deployment

1. Upload all three HTML files to a GitHub repository
2. Go to **Settings → Pages → Source: Deploy from branch (main / root)**
3. Your site will be live at `https://your-username.github.io/your-repo-name/`

## EmailJS Setup

The form uses [EmailJS](https://www.emailjs.com) to send confirmation emails. Credentials are already configured in `index.html`:

- **Service ID:** `service_k707yao`
- **Template ID:** `template_00qxxx4`
- **Public Key:** `lDJvSB7DwOn-7egZP`

Make sure your EmailJS template uses these variables:
`{{first_name}}`, `{{last_name}}`, `{{user_email}}`, `{{milestone}}`, `{{priority}}`, `{{change_type}}`, `{{description}}`, `{{source_entity}}`, `{{source_field}}`, `{{vos_entity}}`, `{{vos_field}}`

Set the **To Email** field in your template to `{{user_email}}`.

## Dashboard

Visit `dashboard.html` to view all submissions. Features include:
- Summary stats (total, urgent, high priority, today)
- Search across all fields
- Filter by priority and milestone
- Click any row to expand full submission details

No login required — share the URL with anyone who needs read-only access.
