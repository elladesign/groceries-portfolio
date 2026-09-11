# Lessons Learned

## Product Lessons

### Meal Planning Is Not Just Recipe Search

Users do not only need more recipes. They need a plan that respects budget, time, servings, existing ingredients, family preferences, and the reality of grocery availability.

### Budget Optimization Has To Happen Early

If the app shows recipes first and only discovers the plan is over budget at checkout, the product promise fails. The recommendation engine needs cost awareness before presenting the plan.

### Pantry Is A Differentiator

Knowing what the user already has can reduce cost and waste. But pantry capture must be easy, editable, and forgiving because recognition will never be perfect.

### Final Review Is A Feature

For grocery, final review should not feel like a weakness. It is a trust feature. The user needs to verify substitutions, coupons, taxes, delivery fees, and checkout details.

## Technical Lessons

### Provider APIs Are Not The Whole Checkout Experience

Product search and cart APIs can help, but provider checkout still controls final availability, substitutions, loyalty pricing, coupons, payment, and scheduling.

### Cart API Success Does Not Guarantee Visible Cart Success

A provider can accept an API request but still filter, replace, delay, or hide items later based on account state, fulfillment mode, delivery address, inventory, or checkout rules.

### Product Matching Must Be Grocery-Safe

Naive keyword matching can return non-food or wrong-category items. Examples of risks:

- cosmetic products for food keywords
- premium/organic products when the app should prefer low-cost staples
- prepared meals when the user needs raw ingredients
- specialty ingredients with weak provider matches

The app needs ingredient normalization, category filters, pantry staples logic, and user review.

### Vision Quality Depends On The Input

Large pantry photos with many overlapping packages are hard. Better UX:

- ask users to photograph fewer items at a time
- let users review detected items
- support manual correction
- merge duplicates
- show persistent errors instead of quick disappearing toasts

## UX Lessons

### Copy Matters

Small wording changes can prevent major confusion. Examples:

- "Cart sent successfully" is clearer than "Connected."
- "Review and confirm what to buy" is clearer than "Pantry gaps."
- "Use what you have" is clearer than technical pantry language.

### Loading States Need To Explain The Work

AI and provider operations can take time. Good loading states should explain what is happening:

- checking pantry items
- estimating ingredient cost
- finding lower-cost meal swaps
- building grocery cart

### Users Need Easy Undo And Recovery

Recipe selection should let users recover from accidental changes. Pantry recognition should let users remove, edit, and manually add items.

## Privacy Lessons

### API Keys Should Not Live In The App

Shared OpenAI, Hugging Face, or grocery provider secrets belong on the backend, not in the iOS app.

### User Photos Need Clear Boundaries

The user should know:

- when a photo stays on device
- when a photo is sent to a backend
- whether it is stored
- how it is used
- how to delete pantry data

### Public Code Needs A Different Setup Than Private Prototype Code

Before open sourcing app code:

- remove live backend URLs
- remove environment files
- rotate any pasted tokens
- add backend authentication and rate limiting
- use placeholders in docs and examples

## Strategy Lesson

The practical MVP is not "multi-store AI grocery autopilot." It is:

> Budget-aware meal planning with pantry memory and grocery cart handoff for final review.

That is narrower, but much more shippable.
