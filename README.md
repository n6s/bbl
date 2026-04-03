# Black Books & Ledgers

Initial marketing site for Jessica LaCario and `blackbooksandledgers.com`.

## Project structure

- `public/index.html` contains the homepage copy and layout
- `public/styles.css` contains the visual design
- `wrangler.jsonc` configures the existing Cloudflare Worker for static asset deploys

## Local development

1. Install dependencies with `npm install`.
2. Run `npm run dev`.
3. Wrangler will serve the site locally using the `public/` directory.

## Deploying with Wrangler

1. Authenticate Wrangler with `npx wrangler login`.
2. Run `npm run deploy`.
3. Wrangler will deploy the contents of `public/` to the existing Worker named `blackbooksandledgers`.

The Worker name in `wrangler.jsonc` intentionally matches the existing Cloudflare project so Workers Builds can connect cleanly.

## Connecting GitHub to Cloudflare Workers Builds

1. Push this repository to GitHub.
2. In Cloudflare, open the `blackbooksandledgers` Worker.
3. Go to `Settings` -> `Builds`.
4. Connect the GitHub repository.
5. Set the production branch to `main`.
6. Leave the build command blank.
7. Set the deploy command to `npm run deploy`.

Cloudflare's current docs note that the Worker name in the dashboard must match the `name` field in `wrangler.jsonc`, or the build will fail.

## Notes for the next pass

- Replace broad service wording with Jessica's final service list and niche.
- Add a form or scheduling link only if she wants a stronger lead capture flow.
- If Jessica later wants full mailbox sending from the domain, move to Google Workspace or add a dedicated outbound SMTP provider.
