# Privacy And Security Notes

## Public Repo Policy

This public portfolio repo should contain product and architecture documentation only.

Do not include:

- application source code from the private prototype
- live backend URLs
- API keys
- OAuth client secrets
- access tokens
- refresh tokens
- `.env` files
- local token files
- real pantry photos
- private account screenshots
- personal email addresses
- exact home address or household data

## Secret Handling

Secrets belong in the deployment provider's environment variable manager.

Use host-managed secret names and never commit actual values.

## Mobile App Key Policy

The iOS app should not contain:

- OpenAI keys
- Hugging Face tokens
- grocery provider client secrets
- shared refresh tokens

The app should call a backend, and the backend should call external providers.

## Backend Exposure Risk

A live backend URL is not technically a secret, but it can still be abused if public endpoints trigger paid model calls or cart handoff attempts.

Before making backend code public or sharing a live backend:

- add authentication
- add rate limiting
- restrict CORS as appropriate
- log abuse signals
- avoid unauthenticated expensive AI endpoints
- use test/demo endpoints for public demos

## Pantry Photo Privacy

Pantry photos may reveal:

- dietary habits
- household size
- health-related preferences
- brands and spending patterns
- location clues from packaging or receipts

The app should clearly explain:

- whether scanning happens on device or in the cloud
- whether photos are stored
- how detected pantry data is used
- how users can delete pantry items
- whether scans are used for model training

## Recommended Portfolio Language

Use:

> The working prototype is private while provider integrations, user data handling, and backend security are being hardened. This public repo documents the product strategy, architecture, and implementation lessons.

Avoid:

> The full app code is open source and ready for public production use.

That would overstate the current security and provider-readiness posture.
