# Black Books & Ledgers

Marketing site for Black Books & Ledgers and `blackbooksandledgers.com`, deployed to Cloudflare Workers.

## Project structure

- `public/index.html` contains the homepage copy and layout
- `public/styles.css` contains the visual design
- `wrangler.jsonc` configures the existing Cloudflare Worker for static asset deploys

## Local development

1. Install dependencies with `npm install`.
2. Run `npm run dev`.
3. Wrangler will serve the site locally using the `public/` directory.

## Deploying

Pushing to the `main` branch runs the GitHub Actions deploy workflow in `.github/workflows/deploy.yml`.
The workflow installs dependencies and runs `npm exec -- wrangler deploy`, which deploys the contents of
`public/` to the existing Worker named `blackbooksandledgers`.

The repository must have a GitHub secret named `CLOUDFLARE_API_TOKEN` with permission to deploy the Worker.

## Manual deploy

1. Authenticate Wrangler with `npx wrangler login` or set `CLOUDFLARE_API_TOKEN`.
2. Run `npm install` if dependencies are not installed.
3. Run `npm run deploy`.

The Worker name in `wrangler.jsonc` intentionally matches the existing Cloudflare Worker.

## Notes for the next pass

- Keep service wording aligned with the business-centered service list and client experience.
- Add a form or scheduling link only if the business wants a stronger lead capture flow.
- If the business later wants full mailbox sending from the domain, move to Google Workspace or add a dedicated outbound SMTP provider.
