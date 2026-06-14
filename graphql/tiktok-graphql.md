# TikTok GraphQL Schema

## Overview

This conceptual GraphQL schema models the TikTok platform's APIs as a unified graph. It is derived from three primary REST API surfaces offered by TikTok for Developers:

- **TikTok for Developers** — content, user data, login kit, and data portability (<https://developers.tiktok.com/>)
- **TikTok API for Business** — advertising, campaign management, audiences, and reporting (<https://business-api.tiktok.com/portal/docs>)
- **TikTok Shop API** — commerce, product catalog, order management, and affiliate programs (<https://partner.tiktokshop.com/>)

The schema is not an official TikTok product. It represents how the platform's capabilities could be expressed in a GraphQL API, enabling a single graph query to span content, advertising, commerce, and creator domains.

## Schema Source

**File:** `tiktok-schema.graphql`
**Source APIs:**
- <https://developers.tiktok.com/doc/overview>
- <https://business-api.tiktok.com/portal/docs>
- <https://partner.tiktokshop.com/docv2/page/tts-api-concepts-overview>
- <https://developers.tiktok.com/doc/data-portability-api-get-started>

## Type Summary

The schema defines the following named types across six domains:

### User & Profile (6 types)
| Type | Description |
|------|-------------|
| `User` | A TikTok user account with profile, stats, and content |
| `TikTokUser` | Lightweight user reference used in relation objects |
| `UserProfile` | Extended public-facing profile information |
| `UserStats` | Aggregated follower, following, like, and video counts |
| `FollowRelation` | A follow relationship between two users |
| `Follower` | A follower entry linking a user to their follower |

### Video & Media (7 types)
| Type | Description |
|------|-------------|
| `Video` | A TikTok video post with all metadata |
| `VideoDetails` | Technical details including format, bitrate, and download URL |
| `VideoStat` | Play, like, comment, share, and save counts per video |
| `VideoCaption` | Caption or subtitle entry for a video |
| `VideoSound` | The sound track associated with a video |
| `VideoEffect` | A visual effect applied to a video |
| `VideoFilter` | A filter applied to a video |

### Music & Sound (4 types)
| Type | Description |
|------|-------------|
| `Music` | A music track available on TikTok |
| `Sound` | Generic sound resource (music or original) |
| `OriginalSound` | An original sound created by a TikTok user |
| `MusicDetail` | Extended details: album, genre, license type |

### HashTag & Challenge (3 types)
| Type | Description |
|------|-------------|
| `HashTag` | A hashtag used on TikTok with stats and associated videos |
| `HashTagChallenge` | A branded or community hashtag challenge |
| `HashTagStat` | Video count, view count, and participant count for a hashtag |

### Engagement (5 types)
| Type | Description |
|------|-------------|
| `Comment` | A comment on a TikTok video |
| `CommentReply` | A reply to a TikTok comment |
| `Like` | A like interaction on a video or comment |
| `Share` | A share interaction for a video |
| `Save` | A save/bookmark interaction on a video |

### Stories (2 types)
| Type | Description |
|------|-------------|
| `Story` | A TikTok Story post |
| `StoryVideo` | A video segment within a Story |

### LIVE & Streaming (5 types)
| Type | Description |
|------|-------------|
| `LIVE` | An active or historical TikTok LIVE session |
| `LiveStream` | Alias for a LIVE session with revenue summary |
| `LiveRoom` | A TikTok LIVE room configuration |
| `GiftRecord` | A gift sent during a TikTok LIVE |
| `DiamondWallet` | A creator's diamond wallet balance from LIVE gifts |

### Creator (3 types)
| Type | Description |
|------|-------------|
| `Creator` | A TikTok content creator |
| `CreatorMarketplace` | Marketplace profile for brand collaboration |
| `CreatorProfile` | Detailed profile including categories and engagement rate |

### Brand & Business (3 types)
| Type | Description |
|------|-------------|
| `Brand` | A brand entity on TikTok for Creator Marketplace |
| `BrandSuitable` | Brand suitability metadata for content safety |
| `BusinessAccount` | A TikTok business account |

### Advertising (11 types)
| Type | Description |
|------|-------------|
| `AdAccount` | A TikTok Ads Manager account |
| `Campaign` | An advertising campaign with objective and budget |
| `AdGroup` | An ad group within a campaign |
| `AdGroupAudience` | Audience targeting configuration for an ad group |
| `TikTokAd` | A TikTok ad creative unit |
| `SparkAd` | A Spark Ad boosting an organic video |
| `DynamicAd` | A dynamic ad auto-generating creative from a catalog |
| `AdCreative` | Creative assets for a TikTok ad |
| `AdPlacement` | An ad placement option on TikTok |
| `AdTarget` | Generic targeting configuration |
| `CustomAudience` | A custom audience segment for ads targeting |
| `LookAlike` | A lookalike audience based on a source custom audience |

### Conversion & Pixels (3 types)
| Type | Description |
|------|-------------|
| `ConversionPixel` | A TikTok Pixel for web event tracking |
| `WebEvent` | A web conversion event tracked by a Pixel |
| `AppEvent` | An in-app conversion event tracked via SDK or API |

### Commerce & Shop (6 types)
| Type | Description |
|------|-------------|
| `CatalogProduct` | A product in the TikTok Shop catalog |
| `ProductGroup` | A product group or collection |
| `ShoppingFeature` | TikTok Shopping feature integration metadata |
| `TikTokShop` | A TikTok Shop storefront |
| `Order` | A shop order |
| `Affiliate` | A TikTok affiliate program participant |
| `AffiliateTask` | A specific task assigned to an affiliate creator |

### Auth & API Management (4 types)
| Type | Description |
|------|-------------|
| `OAuthApp` | A registered TikTok OAuth application |
| `AccessToken` | An OAuth access token for a TikTok user |
| `APIKey` | An API key for server-to-server authentication |
| `Webhook` | A webhook subscription for TikTok event notifications |

### Enumerations (7 types)
| Enum | Values |
|------|--------|
| `VideoStatus` | PUBLIC, PRIVATE, FRIENDS_ONLY, DRAFT, DELETED |
| `AdStatus` | ENABLE, DISABLE, DELETE, CAMPAIGN_DISABLE |
| `CampaignObjective` | AWARENESS, REACH, VIDEO_VIEWS, APP_INSTALL, WEBSITE_CONVERSIONS, LEAD_GENERATION, SHOP_PURCHASES |
| `AudienceGender` | MALE, FEMALE, ALL |
| `OrderStatus` | UNPAID, AWAITING_SHIPMENT, AWAITING_COLLECTION, IN_TRANSIT, DELIVERED, COMPLETED, CANCELLED, IN_CANCEL, PARTIALLY_RETURNING, REVERSE_IN_PROGRESS, COMPLETED_RETURN |
| `LiveStatus` | ACTIVE, ENDED, PAUSED |
| `SharePlatform` | TIKTOK, INSTAGRAM, FACEBOOK, TWITTER, WHATSAPP, SMS, COPY_LINK |
| `CreatorTier` | STANDARD, RISING, ESTABLISHED, TOP |
| `AffiliateTaskStatus` | PENDING, IN_PROGRESS, COMPLETED, CANCELLED |

### Connection / Pagination Types (9 types)
Cursor-based pagination wrappers for: `VideoConnection`, `CommentConnection`, `CommentReplyConnection`, `FollowerConnection`, `FollowRelationConnection`, `CampaignConnection`, `AdGroupConnection`, `TikTokAdConnection`, `CatalogProductConnection`, `OrderConnection`, plus `PageInfo`.

## Example Queries

### Fetch authenticated user's recent videos

```graphql
query MyRecentVideos {
  me {
    openId
    displayName
    stats {
      followerCount
      videoCount
    }
    videos(first: 10) {
      edges {
        node {
          id
          title
          stats {
            playCount
            likeCount
          }
          createTime
        }
      }
    }
  }
}
```

### Retrieve campaign performance

```graphql
query CampaignPerformance($adAccountId: ID!) {
  adAccount(adAccountId: $adAccountId) {
    name
    currency
    campaigns(first: 20) {
      edges {
        node {
          id
          name
          objective
          status
          budget
          adGroups(first: 5) {
            edges {
              node {
                id
                name
                ads(first: 5) {
                  edges {
                    node {
                      id
                      name
                      impressions
                      clicks
                      spend
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
}
```

### Fetch TikTok Shop orders

```graphql
query PendingOrders($shopId: ID!) {
  shop(shopId: $shopId) {
    name
    orders(status: AWAITING_SHIPMENT, first: 50) {
      edges {
        node {
          id
          status
          totalAmount
          currency
          createdAt
        }
      }
    }
  }
}
```

### Lookup a hashtag challenge

```graphql
query HashTagInfo($name: String!) {
  hashtag(name: $name) {
    id
    name
    stats {
      videoCount
      viewCount
    }
    challenge {
      title
      description
      startDate
      endDate
      sponsorBrand {
        name
        logoUrl
      }
    }
  }
}
```

## Authentication

TikTok APIs use OAuth 2.0. The `AccessToken` type models the token response. For advertising and shop APIs, a separate app credential flow is used via the `APIKey` type. Webhooks are secured with a shared secret field on the `Webhook` type.

## Related Resources

- TikTok Developer Portal: <https://developers.tiktok.com/>
- Business API Portal: <https://business-api.tiktok.com/portal>
- TikTok Shop Partner Portal: <https://partner.tiktokshop.com/>
- GitHub Organization: <https://github.com/tiktok>
- TikTok SDK: <https://github.com/tiktok/tiktok-business-api-sdk>
- Changelog: <https://developers.tiktok.com/doc/changelog>
- Status Page: <https://status.tiktok.com/>
