# Case Study

## Overview

MealCart is a budget-aware meal planning assistant designed around one practical user goal:

> Plan meals I can actually afford, using what I already have, and help me get the groceries into a cart faster.

The project started as a broad multi-store grocery assistant idea and narrowed into a more realistic MVP after provider research and hands-on prototype testing.

## Target User

The first target user is a busy household planner who:

- cooks several meals a week
- wants to stay within a grocery budget
- has pantry/fridge items that often get forgotten
- wants recipe ideas but does not want an overly complex meal planning system
- still wants to verify the final grocery cart before checkout

## Core User Flow

1. The user starts a plan and sets a weekly budget.
2. The app asks how many meals and people to plan for.
3. The app can account for known pantry items.
4. The app recommends meals that are intended to stay within budget.
5. The user reviews, changes, favorites, or rejects recipes.
6. The app builds a consolidated ingredient list.
7. The user confirms what should be bought.
8. The app prepares a grocery cart handoff or shopping checklist.
9. The user finishes final review and checkout in the grocery provider's app or website.

## Key Product Decisions

### Budget First

The main differentiator is not "more recipes." It is budget-aware planning. The app should recommend complete meal plans that fit the user's constraints before the shopping list stage.

### Pantry First

Pantry recognition is a differentiator because every item already at home is a chance to reduce spend and waste.

### Human Review

The app should not pretend grocery checkout is fully solved. Availability, substitutions, coupons, delivery windows, fees, taxes, and payment still need provider-side review.

### Provider Handoff, Not Automated Checkout

For MVP, the app focuses on preparing a good cart or shopping checklist and handing the user off to the provider for final review.

## Prototype Learnings

### Pantry Recognition

Pantry photo recognition is useful, but accuracy depends heavily on photo quality. Photos with many cans, sideways labels, partial labels, glare, or overlapping packages are hard.

A practical flow needs:

- user coaching for simpler photos
- detected-item review before saving
- manual edit and delete
- duplicate merging, such as combining three visible tomato sauce cans into one item with quantity
- a fallback path when recognition fails

### On-Device Recognition

Apple Vision OCR and barcode scanning are useful but limited. They can read some label text and barcodes, but they do not fully understand grocery products from messy pantry scenes.

The strongest long-term local approach appears to be a hybrid pipeline:

- detect packages/cans/bottles locally
- crop each candidate item
- run OCR on each crop
- use barcode lookup where visible
- apply grocery-specific rules
- use cloud AI only as an optional fallback

### Grocery Cart Handoff

Cart APIs can report success before the user sees a clean final cart. The app must treat provider checkout as the source of truth.

The UX should say:

- the app helped build the cart
- the user still needs to review substitutions, availability, coupons, delivery fees, taxes, scheduling, and payment
- if any item is missing or unavailable, the app should support fallback suggestions

## Current MVP Shape

MealCart is best framed as:

> A budget-aware meal planning assistant that uses your pantry first and helps prepare a grocery cart for final review.

Not:

> A fully automated grocery ordering app.

## Portfolio Takeaway

This project shows the difference between a promising AI demo and a usable product:

- AI output must be reviewed.
- Grocery availability is dynamic.
- Cart handoff needs recovery states.
- Budget optimization must happen before the user confirms meals.
- The app must explain uncertainty instead of hiding it.
