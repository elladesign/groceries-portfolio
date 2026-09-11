# Product Roadmap

## Phase 1: Private Prototype

Goal: prove the end-to-end experience for one household.

Core work:

- Native iOS meal planning flow
- Pantry photo and manual pantry updates
- Recipe selection and saved meal plans
- Budget-aware shopping list
- Grocery provider cart handoff
- Clear final review copy

Success criteria:

- user can create a meal plan
- user can account for pantry items
- user can review detected pantry items
- user can confirm what to buy
- user can send or recreate a grocery cart
- user understands final checkout still happens in the grocery provider

## Phase 2: Reliability And Polish

Goal: make the prototype feel trustworthy.

Core work:

- Improve visual design system
- Improve onboarding copy
- Improve pantry scan coaching
- Add better recipe variety
- Add stronger ingredient normalization
- Add safer grocery product matching
- Add over-budget prevention before recipe confirmation
- Add better loading and error states
- Add saved plan naming, search, and delete

Success criteria:

- fewer confusing states
- fewer irrelevant grocery matches
- fewer over-budget plans
- pantry edit flow is easy
- saved meal plans are easy to revisit

## Phase 3: Data Persistence

Goal: move beyond local-only prototype storage.

Possible backend data store:

- Supabase
- Render Postgres
- another hosted Postgres option

Core data:

- users
- households
- preferences
- pantry items
- pantry scans
- saved plans
- favorites
- disliked recipes
- provider connections

Success criteria:

- user data persists across devices
- family use is possible
- provider tokens are stored securely
- pantry and saved plans are not lost if the app is reinstalled

## Phase 4: On-Device Pantry Recognition

Goal: reduce dependency on paid AI tokens and improve privacy.

Candidate pipeline:

- local package/object detection
- crop candidate grocery items
- local OCR
- barcode detection
- grocery-specific normalization
- cloud fallback only for low-confidence scans

Success criteria:

- useful detection without OpenAI/HF key
- fewer false positives
- user can edit every detected item
- privacy story becomes simpler

## Phase 5: Public Portfolio Release

Goal: make the project understandable to recruiters, collaborators, and portfolio viewers.

Public release contents:

- case study
- architecture diagram
- roadmap
- lessons learned
- sanitized screenshots or demo GIFs
- privacy notes
- no private code
- no secrets
- no live backend URL

Success criteria:

- someone can understand the product and technical judgment in under five minutes
- deeper docs show real constraints and decisions
- the private app remains safe

## Phase 6: App Store Readiness

Goal: make a real installable app that can be shared beyond the original household.

Core work:

- proper app privacy policy
- support contact
- user data deletion path
- backend authentication
- rate limiting
- app analytics with privacy review
- production database
- crash reporting
- provider terms review
- App Store screenshots and metadata

Success criteria:

- the app can be reviewed safely
- user data handling is documented
- backend costs are controlled
- secrets are not exposed
