# TikTok

TikTok is a short-form social video platform offering developers REST APIs for advertising, e-commerce, content discovery, and platform integrations. Key products include the TikTok API for Business (advertising and campaign management), TikTok Shop API (seller product and order management), and the Data Portability API.

**Human URL:** https://developers.tiktok.com/

## APIs

| Name | Description |
|---|---|
| [TikTok API for Business](https://business-api.tiktok.com/portal/docs) | Advertising campaign, ad group, creative, and reporting management |
| [TikTok Shop API](https://partner.tiktokshop.com/docv2/page/tts-api-concepts-overview) | Seller product catalog, order, and logistics management |
| [TikTok Data Portability API](https://developers.tiktok.com/doc/data-portability-api-get-started) | User data export operations |

## OpenAPI Specifications

| Specification | Description |
|---|---|
| [TikTok Business API](openapi/tiktok-business-openapi.yml) | Advertising campaigns, ad groups, ads, and reporting |
| [TikTok Shop API](openapi/tiktok-shop-openapi.yml) | Products, orders, logistics, and payments |
| [TikTok Data Portability API](openapi/tiktok-data-portability-openapi.yml) | User data export tasks |

## Capabilities

| Capability | APIs Used | Description |
|---|---|---|
| [Advertising Management](capabilities/advertising-management.yaml) | Business API | Full campaign lifecycle and performance reporting |
| [Shop Operations](capabilities/shop-operations.yaml) | Shop API | Product, order, and payment management |

### Shared API Definitions

| Shared Definition | Description |
|---|---|
| [business-api.yaml](capabilities/shared/business-api.yaml) | TikTok Business API consumed definition |
| [shop-api.yaml](capabilities/shared/shop-api.yaml) | TikTok Shop API consumed definition |

## Rules

| Ruleset | Description |
|---|---|
| [tiktok-rules.yml](rules/tiktok-rules.yml) | Spectral ruleset for TikTok API conventions |

## Schemas

| Schema | Description |
|---|---|
| [tiktok-campaign-schema.json](json-schema/tiktok-campaign-schema.json) | JSON Schema for TikTok advertising campaign |
| [tiktok-order-schema.json](json-schema/tiktok-order-schema.json) | JSON Schema for TikTok Shop order |

## Structures

| Structure | Description |
|---|---|
| [tiktok-campaign-structure.json](json-structure/tiktok-campaign-structure.json) | Campaign object field structure |

## JSON-LD

| Context | Description |
|---|---|
| [tiktok-context.jsonld](json-ld/tiktok-context.jsonld) | JSON-LD context mapping to schema.org |

## Examples

| Example | Description |
|---|---|
| [Get Campaigns](examples/tiktok-business-getCampaigns-example.json) | Example advertising campaign retrieval |
| [List Orders](examples/tiktok-shop-listOrders-example.json) | Example TikTok Shop order listing |

## Vocabulary

| Vocabulary | Description |
|---|---|
| [tiktok-vocabulary.yml](vocabulary/tiktok-vocabulary.yml) | TikTok platform vocabulary |

## Common Properties

- **Website:** https://www.tiktok.com/
- **Developer Portal:** https://developers.tiktok.com/
- **Business API Portal:** https://business-api.tiktok.com/portal
- **Shop Partner Portal:** https://partner.tiktokshop.com/
- **GitHub:** https://github.com/tiktok
- **Terms of Service:** https://developers.tiktok.com/doc/tiktok-api-terms-of-service

## Maintainers

**Kin Lane** (kin@apievangelist.com)
