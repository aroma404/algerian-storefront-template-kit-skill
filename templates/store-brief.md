# Store Implementation Brief

Use this file as the approved source of truth before implementation. Replace every blank with a confirmed value or write `Pending — user decision required`. Do not silently infer decisions that affect purchases, persistence, security, or legal content.

## Store identity

| Field | Approved value |
|---|---|
| Store name |  |
| Short description |  |
| Contact email |  |
| Visible language |  |
| Country and locale |  |
| Currency and format |  |
| Logo and brand assets |  |
| Licensed image sources |  |

## Template and experience

| Field | Approved value |
|---|---|
| Template ID |  |
| Template-owned runtime confirmed | Yes / No |
| Template-owned CSS confirmed | Yes / No |
| Required navigation |  |
| Required home sections |  |
| Required catalog behavior |  |
| Required product behavior |  |
| Required cart behavior |  |
| Required checkout behavior |  |
| Desktop layout |  |
| Tablet layout |  |
| Mobile layout |  |

## Catalog

For every product, confirm the following fields in the editable store source:

| Field | Value or status |
|---|---|
| Product ID and SKU |  |
| Name and description |  |
| Price in the approved currency |  |
| Initial stock |  |
| Options or variants |  |
| Cover image URL |  |
| Ordered gallery image URLs |  |
| Category |  |
| Delivery restrictions |  |

Do not add fabricated reviews, ratings, testimonials, customer counts, or sales claims.

## Delivery and payment

| Field | Approved value |
|---|---|
| Delivery zones or Wilayas |  |
| Delivery calculation |  |
| Delivery SLA text |  |
| Payment methods shown |  |
| Checkout mode | Informational / internal order / external provider |
| Order states |  |
| Customer notifications |  |
| Refund or cancellation policy |  |

## Core and UI architecture

| Area | Decision |
|---|---|
| Core registry entry point | `client/src/core/registry.ts` |
| Registry metadata | `client/src/core/registry.json` |
| UI entry point | `client/src/ui/` |
| Template runtime | `templates/<template-id>/runtime.tsx` |
| Template styles | `templates/<template-id>/runtime.css` |
| Server entry point | `server/index.ts` |
| Internal persistence file | `data/store-state.json` or approved path |
| Express port |  |
| External database | Not permitted by this architecture |

## Plugins and integrations

| Plugin or integration | Enabled? | Configuration status |
|---|---|---|
|  |  |  |
|  |  |  |
|  |  |  |

Keep secrets server-side and outside source control. Do not add a provider until its security, webhook, failure, and order-state behavior is defined.

## Acceptance criteria

The implementation is ready for delivery only when the following are confirmed:

- The store runs from one folder and one Express process.
- The selected template owns its JSX, CSS, navigation, pages, and responsive behavior.
- Shared imports use the core registry facade.
- UI code does not reach into infrastructure through scattered deep imports.
- Product prices and stock are authoritative on the server.
- Invalid checkout input is rejected.
- Competing orders cannot oversell tracked stock.
- Catalog, cart, checkout, order tracking, and product galleries work.
- Desktop, tablet, and mobile layouts are inspected.
- Tests, type checking, production build, and clean archive validation pass.

## Approval

Approved by:  

Approval date:  

Open decisions before implementation:  
