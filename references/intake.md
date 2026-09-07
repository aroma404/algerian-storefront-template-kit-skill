# Store Intake Questionnaire

Use this questionnaire progressively. Ask no more than one small group at a time, skip questions already answered by the user or clearly established by the supplied template, and record unresolved decisions instead of guessing.

## Stage 1: purpose and audience

Ask:

1. What does the store sell, and what is the primary customer action?
2. Who is the target audience and which regions should the store serve?
3. Which visible language should the storefront use?
4. Which currency and price format should be displayed?

For an Algerian store, defaulting to English and DZD is acceptable only when the user confirms it or the project brief already establishes it.

## Stage 2: identity and template

Ask:

1. What is the store name, short description, and contact email?
2. Which template ID should be used?
3. Should the supplied template identity be preserved, or should the store receive a new visual identity?
4. Which brand colors, logo, type preferences, and licensed assets are available?

Do not treat a palette change as a template rebuild. The selected template must retain its own composition and responsive behavior.

## Stage 3: catalog and content

Ask:

1. What products or categories must be included at launch?
2. For each product, what are the name, description, price, SKU, stock quantity, options, and delivery restrictions?
3. Which cover image and ordered gallery images are available for each product?
4. Which home sections, product details, policies, FAQ, about, and contact content are required?

Never invent reviews, ratings, testimonials, customer counts, or sales claims. Mark missing assets as pending and request them from the user.

## Stage 4: delivery and payment

Ask:

1. Which delivery zones and Wilayas are served?
2. Is delivery priced by zone, product, order value, or another rule?
3. Which payment methods should be shown?
4. Is checkout informational, cash-on-delivery, or connected to a real payment provider?
5. Which order states and customer notifications are required?

Do not assume cash on delivery, CIB, Edahabia, delivery fees, or coverage. Treat payment credentials and webhook secrets as server-only requirements.

## Stage 5: integrations and operations

Ask:

1. Are analytics, messaging, email, shipping, or inventory integrations required?
2. Who will edit products and internal data after delivery?
3. Where will the internal JSON state file be stored persistently?
4. Which domain, hosting, backup, and deployment constraints apply?
5. Are there accessibility, performance, SEO, or legal requirements?

Do not add an external database or separate API service unless the user explicitly changes the architecture requirement.

## Approval checkpoint

Before implementation, summarize:

| Decision | Approved value |
|---|---|
| Store purpose and audience |  |
| Visible language |  |
| Currency and locale |  |
| Template ID |  |
| Catalog and image status |  |
| Delivery rules |  |
| Payment method |  |
| Required pages |  |
| Plugins and integrations |  |
| Internal data path |  |
| Deployment constraints |  |

Ask the user to approve or correct this summary. Do not begin irreversible integration or real-payment work before approval.
