# MealCart: Budget-Aware Meal Planning Case Study

MealCart is a product case study for a budget-aware grocery and meal planning app.

The app concept helps a household set a grocery budget, use pantry items first, generate practical meal plans, and prepare a grocery cart handoff for checkout with a supported grocery provider.

![MealCart product screens](./assets/screenshots/overview.png)

## Problem

Weekly grocery planning is fragmented.

People often have to:

- decide what to cook
- remember what they already have
- compare recipes against budget
- estimate grocery totals
- search for substitutions
- rebuild the same ingredient list inside a grocery app
- review availability, coupons, substitutions, taxes, delivery fees, and checkout manually

MealCart explores whether an assistant can make that workflow faster without removing the user's final control over what they buy.

## Product Direction

The current MVP direction is:

- Native iOS experience for personal and family meal planning.
- Budget-first recipe recommendations.
- Pantry-aware planning so existing ingredients reduce grocery spend.
- Grocery-provider handoff instead of fully automated checkout.
- Clear final review before the user buys anything.
- Privacy-conscious architecture that keeps provider tokens and AI keys out of the app.

## Public Contents

- [Case Study](./case-study.md)
- [Architecture](./architecture.md)
- [Lessons Learned](./lessons-learned.md)
- [Product Roadmap](./roadmap.md)
- [Privacy And Security Notes](./privacy-and-security.md)

## Demo Screens

These screens use sanitized sample data and generated food imagery. They are included to show the intended product direction without exposing private app source code, pantry photos, user accounts, or backend details.

| Plan start | Pantry | Meal plan | Shopping list |
| --- | --- | --- | --- |
| ![Plan start screen](./assets/screenshots/01-plan-start.png) | ![Pantry screen](./assets/screenshots/02-pantry.png) | ![Meal plan screen](./assets/screenshots/03-meal-plan.png) | ![Shopping list screen](./assets/screenshots/04-shopping-list.png) |

## What Is Not Included

This public repo does not include:

- private app source code
- live backend URLs
- API keys
- OAuth client secrets
- user tokens
- personal pantry photos
- private test account details

## Portfolio Summary

MealCart demonstrates product thinking across:

- AI-assisted meal planning
- OCR and vision-based pantry recognition
- grocery API feasibility
- OAuth and cart handoff constraints
- budget-aware recommendation design
- iOS UX flows for review, confirmation, and recovery
- practical privacy and deployment tradeoffs

## Status

Private working prototype in progress.

Public status: case study and product documentation ready for portfolio review.
