# Architecture

## High-Level Architecture

```text
iOS App
  |
  | HTTPS
  v
Backend API
  |
  +-- Pantry recognition adapter
  +-- Meal planning and optimization adapter
  +-- Grocery provider adapter
  +-- Token and connection storage
  +-- Future user data store
```

## iOS App Responsibilities

The iOS app owns:

- onboarding
- planning inputs
- pantry review and edits
- meal selection
- recipe preview
- saved plans
- local preference capture
- user-facing loading and recovery states
- final shopping review UX

The app should not store provider client secrets or shared AI service keys.

## Backend Responsibilities

The backend owns:

- API key storage
- grocery provider OAuth callbacks
- token refresh
- provider API calls
- cart handoff
- pantry recognition calls when cloud vision is used
- meal optimization calls when cloud AI is used
- server-side validation and rate limiting

## Data Model Direction

Future persistent entities:

- `User`
- `Household`
- `Preference`
- `PantryItem`
- `PantryScan`
- `Recipe`
- `FavoriteRecipe`
- `DislikedRecipe`
- `SavedMealPlan`
- `MealPlanRecipe`
- `ShoppingListItem`
- `ProviderConnection`
- `CartHandoff`

## Pantry Recognition Options

### Cloud Vision

Pros:

- best semantic understanding
- handles messy pantry scenes better
- can infer product types from partial labels and packaging context

Cons:

- costs money
- requires network
- adds latency
- sends user-selected photos to a backend/model provider
- requires strong privacy copy and retention rules

### On-Device OCR

Pros:

- private
- fast
- no token cost
- works offline for text extraction

Cons:

- weak when labels are angled, small, blocked, glossy, or split across cans
- does not understand product context deeply
- needs review and correction

### On-Device Model

Pros:

- private
- no per-scan token cost
- can run before OCR to find package/can regions

Cons:

- model size matters
- generic models may detect "can" or "bottle" but not "bamboo shoots"
- converting and shipping a useful product detector requires model evaluation
- exact grocery item recognition still needs OCR, barcode lookup, or product rules

## Recommended Long-Term Recognition Pipeline

```text
User-selected photo
  |
  +-- Local image quality checks
  +-- Local object/package detection
  +-- Crop likely product regions
  +-- OCR each crop
  +-- Barcode scan
  +-- Grocery-specific normalization
  +-- Duplicate merge and quantity estimate
  +-- User review
  +-- Optional cloud fallback when confidence is low
```

## Public Release Architecture Note

For a public portfolio repo, do not include:

- live backend URLs
- provider client secrets
- refresh tokens
- user account identifiers
- pantry photos

Document required environment variables by purpose only, without committing names tied to real provider credentials or any actual values.
