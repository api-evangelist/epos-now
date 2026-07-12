# Epos Now (epos-now)

Epos Now is a cloud-based point of sale (POS) platform for retail and hospitality businesses, pairing countertop and mobile till hardware with a cloud Back Office for products, inventory, customers, staff, reporting, and payments. The EposNow HQ REST API lets developers programmatically read and write that cloud data - products, categories, transactions (sales), customers, stock, tax rates, and devices - using per-device HTTP Basic authentication, with Webhooks for event notifications.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/epos-now/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/epos-now/refs/heads/main/apis.yml)

## Access Model (Honest Notes)

- **Not a standalone metered API.** Epos Now is sold as a commercial per-till POS subscription (optionally bundled with hardware). The REST API is included with a subscription, not billed per call.
- **Per-device credentials.** API access is enabled per API Device registered under **Web Integrations** in the Epos Now Back Office, and provisioned through the Epos Now AppStore. Each API Device consumes one of the account's device licenses and has its own API Key/Secret pair (regenerable). The access token differs for every registered device.
- **HTTP Basic auth.** The access token is `Base64("API Key:API Secret")` (key, a colon, secret, no spaces), sent as `Authorization: Basic {token}`.
- **Proprietary, closed-source SaaS.** There is no open-source or self-hostable server; the API is a hosted cloud service at `https://api.eposnowhq.com`.
- **V2 vs V4.** This catalog models the documented **V2** surface (`/api/V2`). Epos Now marks V2 as deprecated in favor of a newer **V4 / "Global"** API (`/api/v4`) that reorganizes the same domains; V4 per-resource paths are not fully enumerated in public docs.
- **Numbers are indicative.** Pricing and rate limits below are drawn from public/third-party sources and vary by region (UK vs US), promotion, and contract; they are flagged unconfirmed until reconciled against a current Epos Now quote.

## Tags

- Point of Sale
- POS
- Retail
- Hospitality
- Payments
- Inventory
- Commerce
- Ecommerce

## Timestamps

- **Created:** 2026-07-11
- **Modified:** 2026-07-11

## APIs

### Epos Now Products API

Create, read, update, and delete the product catalog that drives the till - products, prices, barcodes, and their category assignments. Paginated listing at 200 records per page. Core to any point of sale, catalog sync, or retail integration.

- **Human URL:** [https://developer.eposnowhq.com/Docs/Api?endpoint=Product](https://developer.eposnowhq.com/Docs/Api?endpoint=Product)
- **Base URL:** `https://api.eposnowhq.com/api/V2`

#### Tags

- Point of Sale
- Products
- Catalog
- Retail

#### Properties

- [Documentation](https://developer.eposnowhq.com/)
- [API Reference](https://developer.eposnowhq.com/Docs/Api?endpoint=Product)
- [OpenAPI](openapi/epos-now-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/epos-now.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/epos-now.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Epos Now Categories API

Manage the product categories used to organize the catalog and the till layout - list, retrieve, create, update, and delete categories that group products for merchandising and reporting.

- **Human URL:** [https://developer.eposnowhq.com/Docs/Api?endpoint=Category](https://developer.eposnowhq.com/Docs/Api?endpoint=Category)
- **Base URL:** `https://api.eposnowhq.com/api/V2`

#### Tags

- Point of Sale
- Categories
- Catalog
- Retail

#### Properties

- [API Reference](https://developer.eposnowhq.com/Docs/Api?endpoint=Category)
- [OpenAPI](openapi/epos-now-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/epos-now.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/epos-now.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Epos Now Transactions API

Read and write transactions - the sales records (orders) captured at the point of sale, including line items, tenders, discounts, taxes, and refunds. List paginated at 200 per page, retrieve by ID, and post new transactions for integrations and order flows.

- **Human URL:** [https://developer.eposnowhq.com/Docs/Api?endpoint=Transaction](https://developer.eposnowhq.com/Docs/Api?endpoint=Transaction)
- **Base URL:** `https://api.eposnowhq.com/api/V2`

#### Tags

- Point of Sale
- Transactions
- Sales
- Orders
- Payments

#### Properties

- [API Reference](https://developer.eposnowhq.com/Docs/Api?endpoint=Transaction)
- [OpenAPI](openapi/epos-now-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/epos-now.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/epos-now.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Epos Now Customers API

Manage the customer records behind loyalty, accounts, and CRM sync - list, retrieve, create, update, and delete customers linked to transactions at the point of sale.

- **Human URL:** [https://developer.eposnowhq.com/Docs/Api?endpoint=Customer](https://developer.eposnowhq.com/Docs/Api?endpoint=Customer)
- **Base URL:** `https://api.eposnowhq.com/api/V2`

#### Tags

- Point of Sale
- Customers
- Loyalty
- CRM

#### Properties

- [API Reference](https://developer.eposnowhq.com/Docs/Api?endpoint=Customer)
- [OpenAPI](openapi/epos-now-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/epos-now.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/epos-now.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Epos Now Stock API

Read stock levels per product and manage stock control - product stock, stock transfers between locations, suppliers, and purchase orders - to keep inventory in sync across a retail estate.

- **Human URL:** [https://developer.eposnowhq.com/Docs/StockControlIntroduction](https://developer.eposnowhq.com/Docs/StockControlIntroduction)
- **Base URL:** `https://api.eposnowhq.com/api/V2`

#### Tags

- Point of Sale
- Stock
- Inventory
- Retail

#### Properties

- [Documentation](https://developer.eposnowhq.com/Docs/StockControlIntroduction)
- [API Reference](https://developer.eposnowhq.com/Docs/Api?endpoint=ProductStock)
- [OpenAPI](openapi/epos-now-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/epos-now.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/epos-now.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Epos Now Devices and Webhooks API

List the registered tills and API devices on the account, and react to changes in near real time with Webhooks. Webhooks POST an HTTP notification to your endpoint whenever a relevant object changes, carrying `Epos-Object` and `Epos-Action` headers describing what happened.

- **Human URL:** [https://developer.eposnowhq.com/Docs/Webhooks](https://developer.eposnowhq.com/Docs/Webhooks)
- **Base URL:** `https://api.eposnowhq.com/api/V2`

#### Tags

- Point of Sale
- Devices
- Webhooks
- Events

#### Properties

- [Documentation](https://developer.eposnowhq.com/Docs/Webhooks)
- [API Reference](https://developer.eposnowhq.com/Docs/Api?endpoint=Device)
- [OpenAPI](openapi/epos-now-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/epos-now.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/epos-now.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Authentication](authentication/epos-now-authentication.yml)
- [LinkedIn](https://www.linkedin.com/company/epos-now)
- [Website](https://www.eposnow.com/)
- [Documentation](https://developer.eposnowhq.com/)
- [Plans](plans/epos-now-plans-pricing.yml)
- [Rate Limits](rate-limits/epos-now-rate-limits.yml)
- [Fin Ops](finops/epos-now-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
