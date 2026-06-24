# Discord HTTP API — Concrete Endpoint Reference

**1,076 bundle paths + 6 internal endpoints**, each probed live (unauthenticated, 2026-06-20) for base URL + HTTP method. The **Endpoint** column always shows the path/URL — even for unresolved rows.

- **Documented** methods are authoritative (OpenAPI spec); **undocumented** methods were found by probing each verb (listed verb returned 401/400 instead of 405). `POST?` = rejects GET, no standard verb confirmed unauthenticated.
- **Type:** `DOC-API`/`API` = `/api/v9` route · `WEB` = `discord.com/<path>` page · `CDN` = static asset on `cdn.discordapp.com` (needs a real id/hash) · `INTERNAL` = `discord.com/__development/*` staff tool · `NOISE` = bundled filesystem string, not an endpoint · `DEAD` = 404 at both bases (removed page / bare-collection root / fragment).
- `{id}` = a snowflake of the preceding resource · `/@me` = current user. Probes sent the literal `{id}`, so id-only routes are marked `? (id-gated)` — substitute a real snowflake to confirm.

**Counts:** **DOC-API** 84 · **API** 681 · **WEB** 230 · **CDN** 11 · **INTERNAL** 6 · **NOISE** 15 · **DEAD** 55

## Documented API — authoritative methods

| Method(s) | Endpoint (URL / path) | Meaning |
|---|---|---|
| `POST` | `https://discord.com/api/v9/applications/{id}/attachment` | Upload an attachment associated with the given application (operation: upload_application_attachment) |
| `GET, PUT` | `https://discord.com/api/v9/applications/{id}/guilds/{id}/commands/{id}/permissions` | Get/set per-guild slash-command permissions for the given command (operation: get/set_guild_application_command_permissions) |
| `GET, DELETE, PATCH` | `https://discord.com/api/v9/channels/{id}` | Get, update, or delete a specific channel by ID |
| `POST` | `https://discord.com/api/v9/channels/{id}/followers` | Follow an announcement channel into another channel |
| `GET, POST` | `https://discord.com/api/v9/channels/{id}/invites` | List or create invites for a channel |
| `GET, POST` | `https://discord.com/api/v9/channels/{id}/messages` | List or create messages in a channel |
| `GET` | `https://discord.com/api/v9/channels/{id}/messages/pins` | List or create pinned messages in a channel |
| `PUT, DELETE` | `https://discord.com/api/v9/channels/{id}/messages/pins/{id}` | Pin or unpin a specific message in a channel |
| `GET, DELETE, PATCH` | `https://discord.com/api/v9/channels/{id}/messages/{id}` | Get, edit, or delete a specific message in a channel |
| `POST` | `https://discord.com/api/v9/channels/{id}/messages/{id}/crosspost` | Crosspost (publish) an announcement-channel message to following channels |
| `DELETE` | `https://discord.com/api/v9/channels/{id}/messages/{id}/reactions` | Get or clear all reactions on a message |
| `GET, DELETE` | `https://discord.com/api/v9/channels/{id}/messages/{id}/reactions/{id}` | Get users for, add, or remove all reactions of a specific emoji on a message |
| `DELETE` | `https://discord.com/api/v9/channels/{id}/messages/{id}/reactions/{id}/{id}` | Add or remove a specific user's reaction of a given emoji on a message |
| `POST` | `https://discord.com/api/v9/channels/{id}/messages/{id}/threads` | Create a thread starting from a specific message |
| `PUT, DELETE` | `https://discord.com/api/v9/channels/{id}/permissions/{id}` | Edit or delete a channel permission overwrite for a role or member |
| `GET` | `https://discord.com/api/v9/channels/{id}/polls/{id}/answers/{id}` | Get the list of voters for a specific poll answer |
| `POST` | `https://discord.com/api/v9/channels/{id}/polls/{id}/expire` | Immediately end (expire) a poll |
| `PUT, DELETE` | `https://discord.com/api/v9/channels/{id}/recipients/{id}` | Add or remove a specific user from a group DM channel |
| `POST` | `https://discord.com/api/v9/channels/{id}/send-soundboard-sound` | Play a soundboard sound in a voice channel |
| `GET, PUT, DELETE` | `https://discord.com/api/v9/channels/{id}/thread-members/{id}` | Get, add, or remove a specific member of a thread |
| `POST` | `https://discord.com/api/v9/channels/{id}/threads` | List or create threads in a channel |
| `GET` | `https://discord.com/api/v9/channels/{id}/threads/search` | Search threads within a channel |
| `POST` | `https://discord.com/api/v9/channels/{id}/typing` | Trigger the typing indicator in a channel |
| `GET` | `https://discord.com/api/v9/channels/{id}/users/@me/threads/archived/private` | List the current user's archived private threads in a channel |
| `PUT` | `https://discord.com/api/v9/channels/{id}/voice-status` | Get or update the voice channel status text |
| `GET, POST` | `https://discord.com/api/v9/channels/{id}/webhooks` | List or create webhooks for a channel |
| `GET` | `https://discord.com/api/v9/guilds/templates/{id}` | Get a guild template by its template code |
| `GET, PATCH` | `https://discord.com/api/v9/guilds/{id}` | Get or modify a specific guild |
| `GET` | `https://discord.com/api/v9/guilds/{id}/audit-logs` | List the audit-log entries for a guild |
| `GET, POST` | `https://discord.com/api/v9/guilds/{id}/auto-moderation/rules` | List or create AutoMod rules for a guild |
| `GET, DELETE, PATCH` | `https://discord.com/api/v9/guilds/{id}/auto-moderation/rules/{id}` | Get, modify, or delete a specific AutoMod rule in a guild |
| `GET` | `https://discord.com/api/v9/guilds/{id}/bans` | List bans in a guild |
| `GET, PUT, DELETE` | `https://discord.com/api/v9/guilds/{id}/bans/{id}` | Get, create, or remove a ban for a specific user in a guild |
| `POST` | `https://discord.com/api/v9/guilds/{id}/bulk-ban` | Bulk-ban multiple users from a guild |
| `GET, POST, PATCH` | `https://discord.com/api/v9/guilds/{id}/channels` | List, create, or bulk-reorder channels in a guild |
| `GET, POST` | `https://discord.com/api/v9/guilds/{id}/emojis` | List or create custom emojis in a guild |
| `GET, DELETE, PATCH` | `https://discord.com/api/v9/guilds/{id}/emojis/{id}` | Get, modify, or delete a specific custom emoji in a guild |
| `GET` | `https://discord.com/api/v9/guilds/{id}/integrations` | List the integrations of a guild |
| `DELETE` | `https://discord.com/api/v9/guilds/{id}/integrations/{id}` | Get or delete a specific integration in a guild |
| `GET` | `https://discord.com/api/v9/guilds/{id}/invites` | List the invites of a guild |
| `GET` | `https://discord.com/api/v9/guilds/{id}/members` | List the members of a guild |
| `PATCH` | `https://discord.com/api/v9/guilds/{id}/members/@me` | Get or update the current user's own member object in a guild |
| `GET, PUT, DELETE, PATCH` | `https://discord.com/api/v9/guilds/{id}/members/{id}` | Get, add, modify, or remove a specific member in a guild |
| `GET` | `https://discord.com/api/v9/guilds/{id}/messages/search` | Search messages across a guild |
| `GET` | `https://discord.com/api/v9/guilds/{id}/new-member-welcome` | Get the new-member welcome (onboarding home) data for a guild |
| `GET, PUT` | `https://discord.com/api/v9/guilds/{id}/onboarding` | Get or update the onboarding configuration for a guild |
| `GET` | `https://discord.com/api/v9/guilds/{id}/preview` | Get the public preview object for the guild (get_guild_preview) |
| `GET, POST` | `https://discord.com/api/v9/guilds/{id}/prune` | Preview or execute pruning of inactive members from the guild (preview_prune_guild / prune_guild) |
| `GET` | `https://discord.com/api/v9/guilds/{id}/regions` | List the available voice regions for the guild (list_guild_voice_regions) |
| `GET` | `https://discord.com/api/v9/guilds/{id}/requests` | List the guild's join requests / membership applications (get_guild_join_requests) |
| `PATCH` | `https://discord.com/api/v9/guilds/{id}/requests/{id}` | Get/action (approve/deny) a specific guild join request (action_guild_join_request) |
| `GET, POST, PATCH` | `https://discord.com/api/v9/guilds/{id}/roles` | List/create/bulk-update the guild's roles (list_guild_roles / create_guild_role) |
| `GET` | `https://discord.com/api/v9/guilds/{id}/roles/member-counts` | Get the member count per role in the guild (guild_role_member_counts) |
| `GET, DELETE, PATCH` | `https://discord.com/api/v9/guilds/{id}/roles/{id}` | Get/update/delete a specific guild role (get/update/delete_guild_role) |
| `GET, POST` | `https://discord.com/api/v9/guilds/{id}/scheduled-events` | List/create the guild's scheduled events (list/create_guild_scheduled_event) |
| `GET, DELETE, PATCH` | `https://discord.com/api/v9/guilds/{id}/scheduled-events/{id}` | Get/update/delete a specific guild scheduled event |
| `GET, POST` | `https://discord.com/api/v9/guilds/{id}/soundboard-sounds` | List/create the guild's soundboard sounds (list/create_guild_soundboard_sound) |
| `GET, DELETE, PATCH` | `https://discord.com/api/v9/guilds/{id}/soundboard-sounds/{id}` | Get/update/delete a specific guild soundboard sound |
| `GET, POST` | `https://discord.com/api/v9/guilds/{id}/stickers` | List/create the guild's custom stickers (list/create_guild_sticker) |
| `GET, DELETE, PATCH` | `https://discord.com/api/v9/guilds/{id}/stickers/{id}` | Get/update/delete a specific guild custom sticker |
| `GET, POST` | `https://discord.com/api/v9/guilds/{id}/templates` | List/create the guild's server templates (list/create_guild_template) |
| `PUT, DELETE, PATCH` | `https://discord.com/api/v9/guilds/{id}/templates/{id}` | Sync/update/delete a specific guild template by code |
| `GET` | `https://discord.com/api/v9/guilds/{id}/vanity-url` | Get the guild's vanity invite URL (get_guild_vanity_url) |
| `GET, PATCH` | `https://discord.com/api/v9/guilds/{id}/voice-states/{id}` | Get/update the voice state of a specific user in the guild (get/update_voice_state) |
| `GET` | `https://discord.com/api/v9/guilds/{id}/webhooks` | List the guild's webhooks across all channels (get_guild_webhooks) |
| `GET, PATCH` | `https://discord.com/api/v9/guilds/{id}/welcome-screen` | Get/update the guild's welcome screen (get/update_guild_welcome_screen) |
| `GET, PATCH` | `https://discord.com/api/v9/guilds/{id}/widget` | Get/update the guild's widget settings (get/update_guild_widget_settings) |
| `GET` | `https://discord.com/api/v9/oauth2/@me` | Get the current OAuth2 authorization info (token scopes, app, user) for the bearer token |
| `GET, PATCH` | `https://discord.com/api/v9/users/@me` | Get or update the currently authenticated user's account |
| `GET` | `https://discord.com/api/v9/users/@me/applications/{id}/entitlements` | List the current user's entitlements for a given application |
| `POST` | `https://discord.com/api/v9/users/@me/channels` | List the current user's DM channels or create a new DM/group DM |
| `GET` | `https://discord.com/api/v9/users/@me/connections` | List the current user's linked third-party account connections |
| `DELETE` | `https://discord.com/api/v9/users/@me/guilds/{id}` | Leave or fetch the current user's membership in a specific guild |
| `GET` | `https://discord.com/api/v9/users/{id}` | Gets the user object for the given user ID (get_user) |
| `GET` | `https://discord.com/api/v9/voice/regions` | Lists available voice server regions (list_voice_regions) |
| `GET, DELETE` | `https://discord.com/api/v9/invites/{id}` | Resolve, accept, or revoke an invite by code (invite_resolve / invite_revoke) |
| `GET` | `https://discord.com/api/v9/soundboard-default-sounds` | List the default (built-in) soundboard sounds |
| `POST` | `https://discord.com/api/v9/stage-instances` | Create a Stage instance (live audio stage) |
| `GET, DELETE, PATCH` | `https://discord.com/api/v9/stage-instances/{id}` | Fetch, update, or delete the Stage instance for a channel ID |
| `GET` | `https://discord.com/api/v9/sticker-packs` | List available sticker packs |
| `GET` | `https://discord.com/api/v9/sticker-packs/{id}` | Fetch a sticker pack by its pack ID |
| `GET` | `https://discord.com/api/v9/stickers/{id}` | Fetch a sticker by its sticker ID |
| `GET, DELETE, PATCH` | `https://discord.com/api/v9/webhooks/{id}` | Fetches, updates, or deletes a webhook by webhook ID (get_webhook) |
| `GET, POST, DELETE, PATCH` | `https://discord.com/api/v9/webhooks/{id}/{id}` | Executes, fetches, edits, or deletes a webhook via webhook ID and webhook token (execute_webhook) |

## Undocumented API — live /api/v9 routes (methods probed)

| Method(s) | Endpoint (URL / path) | Meaning |
|---|---|---|
| `POST` | `https://discord.com/api/v9/activities` | List available Discord Activities (embedded voice-channel apps/games) |
| `GET` | `https://discord.com/api/v9/activities/discord-config/{id}` | Get the Discord-side configuration for the given activity application |
| `GET` | `https://discord.com/api/v9/activities/shelf` | Get the curated activities shelf (featured/recommended activities) |
| `GET` | `https://discord.com/api/v9/activities/statistics/applications/{id}` | Get activity usage statistics for the given application |
| `GET` | `https://discord.com/api/v9/activities/{id}/test-mode` | Toggle/get test mode for the given activity (developer testing) |
| `POST` | `https://discord.com/api/v9/activities/{id}/{id}` | Access a nested sub-resource of a specific activity (e.g. a specific instance/asset) |
| `POST` | `https://discord.com/api/v9/age-verification/google-wallet/request` | Request age verification via Google Wallet (start the digital-ID flow) |
| `POST` | `https://discord.com/api/v9/age-verification/google-wallet/verify` | Submit/verify the Google Wallet age-verification result |
| `GET` | `https://discord.com/api/v9/age-verification/methods` | List available age-verification methods for the user |
| `POST` | `https://discord.com/api/v9/age-verification/suspended/methods` | List age-verification methods available to a suspended/restricted account |
| `POST` | `https://discord.com/api/v9/age-verification/test` | Test endpoint for the age-verification flow (developer/QA) |
| `POST` | `https://discord.com/api/v9/age-verification/verify` | Submit an age-verification attempt for processing |
| `POST` | `https://discord.com/api/v9/ai/fix-grammar` | AI service to fix grammar in supplied message text |
| `POST` | `https://discord.com/api/v9/ai/summarize-thread/{id}` | AI-generate a summary of the given thread |
| `POST` | `https://discord.com/api/v9/ai/text-transform` | AI service to transform/rewrite supplied text (tone/style changes) |
| `POST` | `https://discord.com/api/v9/ai/title` | AI-generate a title (e.g. for a thread or conversation) |
| `POST` | `https://discord.com/api/v9/ai/translate` | AI service to translate supplied text |
| `GET` | `https://discord.com/api/v9/application-directory-static/applications/{id}` | Get static cached App Directory listing for the given application |
| `GET` | `https://discord.com/api/v9/application-directory-static/applications/{id}/similar` | Get similar/related apps for the given application (static cache) |
| `GET` | `https://discord.com/api/v9/application-directory-static/categories` | List App Directory categories (static cache) |
| `GET` | `https://discord.com/api/v9/application-directory-static/collections` | List App Directory curated collections (static cache) |
| `GET` | `https://discord.com/api/v9/application-directory-static/search` | Search the App Directory (static cache) |
| `GET` | `https://discord.com/api/v9/application-directory/applications/{id}/embed` | Get the embeddable App Directory card for the given application |
| `GET` | `https://discord.com/api/v9/application-directory/search` | Search the App Directory (live) |
| `GET` | `https://discord.com/api/v9/applications` | List/create applications owned by the current user (developer apps) |
| `GET` | `https://discord.com/api/v9/applications/non-games/detectable` | List detectable non-game applications (for rich-presence auto-detection) |
| `GET` | `https://discord.com/api/v9/applications/public` | List public applications |
| `GET` | `https://discord.com/api/v9/applications/storefront/interactions/premium-button/{id}` | Handle a storefront premium (subscribe/buy) button interaction for the given listing |
| `POST` | `https://discord.com/api/v9/applications/{id}/activities/{id}/instances/{id}/leave` | Leave a specific running activity instance of the given application |
| `GET` | `https://discord.com/api/v9/applications/{id}/application-command-index` | Get the searchable slash-command index for the given application |
| `GET` | `https://discord.com/api/v9/applications/{id}/branches` | List build branches for the given application |
| `GET` | `https://discord.com/api/v9/applications/{id}/branches/{id}/builds/live` | Get the live (published) build for the given application branch |
| `POST` | `https://discord.com/api/v9/applications/{id}/branches/{id}/builds/{id}/size` | Get the download size of a specific build on the given application branch |
| `? (id-gated)` | `https://discord.com/api/v9/applications/{id}/branches/{id}/storage` | Access build storage for the given application branch |
| `GET` | `https://discord.com/api/v9/applications/{id}/disclosures` | Get required disclosures/notices for the given application |
| `POST` | `https://discord.com/api/v9/applications/{id}/external-assets` | Proxy/resolve external assets referenced by the given application |
| `GET` | `https://discord.com/api/v9/applications/{id}/managed-links/{id}` | Get/manage a specific managed (short/deep) link for the given application |
| `GET` | `https://discord.com/api/v9/applications/{id}/payment-payout-groups` | List payment payout groups for the given application (monetization payouts) |
| `POST` | `https://discord.com/api/v9/applications/{id}/proxy-tickets` | Issue/get proxy tickets for the given application (media/activity proxying auth) |
| `GET` | `https://discord.com/api/v9/applications/{id}/public` | Get the public profile/metadata for the given application |
| `GET` | `https://discord.com/api/v9/applications/{id}/quick-links/{id}` | Get a specific quick-link for the given application |
| `GET` | `https://discord.com/api/v9/applications/{id}/skus` | List SKUs (purchasable items) for the given application |
| `GET` | `https://discord.com/api/v9/applications/{id}/store-layout` | Get the store page layout configuration for the given application |
| `GET` | `https://discord.com/api/v9/applications/{id}/subscription-group-listings/{id}` | Get a specific subscription-group store listing for the given application |
| `POST` | `https://discord.com/api/v9/applications/{id}/transfer` | Transfer ownership of the given application (to another user/team) |
| `GET` | `https://discord.com/api/v9/applications/{id}/trusted-links/check` | Check whether a URL is a trusted link for the given application |
| `GET` | `https://discord.com/api/v9/applications/{id}/widget-configs` | Get/manage widget configurations for the given application |
| `POST,DELETE` | `https://discord.com/api/v9/attachments/refresh-urls` | Refresh expired signed CDN URLs for a set of attachments |
| `POST,DELETE` | `https://discord.com/api/v9/attachments/report-false-positive` | Report a false-positive content-scan flag on a received attachment |
| `POST,DELETE` | `https://discord.com/api/v9/attachments/sender-report-false-positive` | Report a false-positive content-scan flag on an attachment as the sender |
| `DELETE` | `https://discord.com/api/v9/attachments/{id}` | Access a specific attachment by ID |
| `POST` | `https://discord.com/api/v9/auth/authorize-ip` | Authorize the current IP address (new-location email verification) |
| `POST` | `https://discord.com/api/v9/auth/conditional/finish` | Finish a conditional/passkey (WebAuthn) authentication flow |
| `POST` | `https://discord.com/api/v9/auth/conditional/start` | Start a conditional/passkey (WebAuthn) authentication flow |
| `POST` | `https://discord.com/api/v9/auth/forgot` | Initiate a forgot-password reset for an account |
| `POST` | `https://discord.com/api/v9/auth/handoff` | Start a cross-device login handoff |
| `POST` | `https://discord.com/api/v9/auth/handoff/exchange` | Exchange a login handoff token for an authenticated session |
| `GET` | `https://discord.com/api/v9/auth/location-metadata` | Get location/region metadata used during the auth flow |
| `POST` | `https://discord.com/api/v9/auth/login` | Authenticate a user with credentials (login) |
| `? (id-gated)` | `https://discord.com/api/v9/auth/login/generated-user/{id}` | Log in as a generated/guest user by ID (ephemeral account login) |
| `POST` | `https://discord.com/api/v9/auth/logout` | Log out and invalidate the current session |
| `POST` | `https://discord.com/api/v9/auth/mfa/sms/send` | Send an SMS multi-factor authentication code |
| `POST` | `https://discord.com/api/v9/auth/mfa/{id}` | Submit/verify a multi-factor authentication challenge of the given type |
| `POST` | `https://discord.com/api/v9/auth/one-time-login` | Perform a one-time login (token-based single-use login) |
| `POST` | `https://discord.com/api/v9/auth/password/validate` | Validate a candidate account password (e.g. for sensitive-action re-auth) |
| `POST` | `https://discord.com/api/v9/auth/passwordless/start` | Begin a passwordless login flow (send/initiate a one-time login challenge) |
| `POST` | `https://discord.com/api/v9/auth/register` | Register a new user account |
| `POST` | `https://discord.com/api/v9/auth/register/phone` | Register/complete a new account using a phone number |
| `POST` | `https://discord.com/api/v9/auth/reset` | Initiate an account password reset |
| `POST` | `https://discord.com/api/v9/auth/revert` | Revert a recent account change (e.g. undo an email/password change via a revert token) |
| `GET` | `https://discord.com/api/v9/auth/sessions` | List the current user's active authenticated sessions |
| `POST` | `https://discord.com/api/v9/auth/sessions/debug/notifications` | Debug endpoint for session-related notifications |
| `POST` | `https://discord.com/api/v9/auth/sessions/logout` | Log out / revoke one or more of the user's sessions |
| `POST` | `https://discord.com/api/v9/auth/verify` | Verify the account email address |
| `POST` | `https://discord.com/api/v9/auth/verify/resend` | Resend the account email verification message |
| `POST` | `https://discord.com/api/v9/auth/verify/view-backup-codes-challenge` | Challenge step required before viewing 2FA backup codes |
| `POST` | `https://discord.com/api/v9/billing/apple/acom-subscriptions/migrate` | Migrate Apple App Store subscriptions to Discord-managed billing |
| `POST` | `https://discord.com/api/v9/billing/apple/apply-receipt` | Apply/validate an Apple in-app-purchase receipt to the account |
| `POST` | `https://discord.com/api/v9/billing/apple/jwt-token` | Issue an Apple billing JWT token for App Store transactions |
| `POST` | `https://discord.com/api/v9/billing/gift-card/redeem` | Redeem a gift card / promo code |
| `POST` | `https://discord.com/api/v9/billing/gift-card/view` | View details of a gift card before redeeming |
| `GET` | `https://discord.com/api/v9/billing/orders` | List the current user's billing orders |
| `GET` | `https://discord.com/api/v9/billing/orders/{id}` | Get a specific billing order by ID |
| `POST` | `https://discord.com/api/v9/billing/orders/{id}/discard` | Discard/cancel a pending billing order |
| `PATCH` | `https://discord.com/api/v9/billing/orders/{id}/line-items/{id}` | Get/manage a specific line item within a billing order |
| `POST` | `https://discord.com/api/v9/billing/orders/{id}/sign` | Sign/confirm a billing order to finalize payment |
| `POST` | `https://discord.com/api/v9/billing/popup-bridge/callback` | Generic payment popup-bridge callback (third-party redirect return) |
| `POST` | `https://discord.com/api/v9/billing/popup-bridge/{id}` | Get a specific payment popup-bridge session by ID |
| `POST` | `https://discord.com/api/v9/billing/popup-bridge/{id}/callback` | Callback for a specific payment popup-bridge session |
| `GET` | `https://discord.com/api/v9/billing/popup-bridge/{id}/callback/{id}/{id}` | Nested callback for a payment popup-bridge session/sub-step |
| `POST` | `https://discord.com/api/v9/billing/verify-purchase-request` | Verify a purchase request before completing it |
| `GET` | `https://discord.com/api/v9/channels/@me` | List the current user's DM and group-DM channels |
| `GET` | `https://discord.com/api/v9/channels/preload-messages` | Preload messages across the user's channels (warm-up fetch) |
| `PUT` | `https://discord.com/api/v9/channels/recipients/@me/batch-reject` | Batch-reject pending group-DM recipient invites for the current user |
| `POST` | `https://discord.com/api/v9/channels/{id}/add-safety-warning` | Add a safety warning to a channel |
| `GET` | `https://discord.com/api/v9/channels/{id}/application-command-index` | Get the application-command index for a channel |
| `GET` | `https://discord.com/api/v9/channels/{id}/application-commands/search` | Search application (slash) commands available in a channel |
| `POST` | `https://discord.com/api/v9/channels/{id}/attachments` | Create/upload an attachment (request upload slot) for a channel |
| `POST` | `https://discord.com/api/v9/channels/{id}/blocked-user-warning-dismissal` | Dismiss the blocked-user warning in a channel |
| `GET` | `https://discord.com/api/v9/channels/{id}/call` | Get/manage the active call in a DM or group-DM channel |
| `POST` | `https://discord.com/api/v9/channels/{id}/call/ring` | Ring (start calling) recipients in a channel |
| `POST` | `https://discord.com/api/v9/channels/{id}/call/stop-ringing` | Stop ringing recipients in a channel call |
| `POST` | `https://discord.com/api/v9/channels/{id}/clips-remote-trigger` | Remote-trigger a clip capture in a channel |
| `GET` | `https://discord.com/api/v9/channels/{id}/conversations` | List AI/summary conversations associated with a channel |
| `GET` | `https://discord.com/api/v9/channels/{id}/conversations/{id}` | Get a specific conversation within a channel |
| `POST` | `https://discord.com/api/v9/channels/{id}/custom-call-sounds` | Get/manage custom call sounds for a channel |
| `GET` | `https://discord.com/api/v9/channels/{id}/directory-entries` | List directory entries (server-discovery listings) in a directory channel |
| `GET` | `https://discord.com/api/v9/channels/{id}/directory-entries/counts` | Get counts of directory entries by category in a directory channel |
| `GET` | `https://discord.com/api/v9/channels/{id}/directory-entries/list` | List directory entries in a directory channel |
| `GET` | `https://discord.com/api/v9/channels/{id}/directory-entries/search` | Search directory entries in a directory channel |
| `GET` | `https://discord.com/api/v9/channels/{id}/directory-entry/{id}` | Get/manage a specific directory entry in a directory channel |
| `PATCH` | `https://discord.com/api/v9/channels/{id}/explicit-media` | Get/manage explicit-media settings/flags for a channel |
| `GET` | `https://discord.com/api/v9/channels/{id}/follower-message-stats` | Get follower message statistics for an announcement channel |
| `GET` | `https://discord.com/api/v9/channels/{id}/follower-stats` | Get follower statistics for an announcement channel |
| `POST` | `https://discord.com/api/v9/channels/{id}/greet` | Send a greet/sticker greeting message in a channel |
| `DELETE` | `https://discord.com/api/v9/channels/{id}/integrations/{id}` | Get/manage a specific integration on a channel |
| `DELETE` | `https://discord.com/api/v9/channels/{id}/linked-lobby` | Get/manage the lobby linked to a channel |
| `GET` | `https://discord.com/api/v9/channels/{id}/media-post-preview` | Get a preview for a media post in a forum/media channel |
| `GET` | `https://discord.com/api/v9/channels/{id}/messages/ack` | Acknowledge (mark read) messages in a channel |
| `GET` | `https://discord.com/api/v9/channels/{id}/messages/announcement` | Get/post announcement-type messages in a channel |
| `GET` | `https://discord.com/api/v9/channels/{id}/messages/search` | Search messages within a channel |
| `POST` | `https://discord.com/api/v9/channels/{id}/messages/search/tabs` | Search messages in a channel across multiple result tabs/filters |
| `POST` | `https://discord.com/api/v9/channels/{id}/messages/{id}/ack` | Mark a specific message as read (acknowledge) |
| `GET` | `https://discord.com/api/v9/channels/{id}/messages/{id}/interaction-data` | Fetch interaction (component/command) data for a message |
| `DELETE` | `https://discord.com/api/v9/channels/{id}/messages/{id}/reactions/{id}/{id}/{id}` | Operate on a reaction by emoji/user with an additional burst/super-reaction variant qualifier |
| `POST,PUT,DELETE` | `https://discord.com/api/v9/channels/{id}/pins/ack` | Acknowledge (mark as seen) the pinned messages of a channel |
| `GET` | `https://discord.com/api/v9/channels/{id}/polls/{id}/answers/@me` | Manage the current user's vote on a poll answer |
| `POST` | `https://discord.com/api/v9/channels/{id}/post-data` | Fetch post/forum data associated with a channel |
| `PUT,PATCH,DELETE` | `https://discord.com/api/v9/channels/{id}/recipients/@me` | Add or remove the current user as a recipient of a group DM |
| `POST` | `https://discord.com/api/v9/channels/{id}/safety-warning/report-false-positive` | Report a channel safety warning as a false positive |
| `DELETE` | `https://discord.com/api/v9/channels/{id}/safety-warnings` | List safety warnings shown for a channel |
| `POST` | `https://discord.com/api/v9/channels/{id}/safety-warnings/ack` | Acknowledge (dismiss) a channel's safety warnings |
| `GET` | `https://discord.com/api/v9/channels/{id}/store-listing` | Get the store listing associated with a channel |
| `POST` | `https://discord.com/api/v9/channels/{id}/store-listing/entitlement-grant` | Grant an entitlement from a channel's store listing |
| `GET` | `https://discord.com/api/v9/channels/{id}/store-listings/{id}` | Get a specific store listing for a channel |
| `GET` | `https://discord.com/api/v9/channels/{id}/summaries` | List AI-generated conversation summaries for a channel |
| `GET` | `https://discord.com/api/v9/channels/{id}/summaries/{id}` | Get a specific conversation summary for a channel |
| `POST` | `https://discord.com/api/v9/channels/{id}/tags` | List or create forum/media channel tags |
| `PUT,DELETE` | `https://discord.com/api/v9/channels/{id}/tags/{id}` | Get, edit, or delete a specific forum/media channel tag |
| `PATCH` | `https://discord.com/api/v9/channels/{id}/thread-members/@me/settings` | Get or update the current user's thread member settings (e.g. notifications) |
| `POST` | `https://discord.com/api/v9/channels/{id}/voice-channel-effects` | Send a voice channel effect (e.g. emoji reaction) in a voice channel |
| `POST` | `https://discord.com/api/v9/channels/{id}/voice-hangout` | Manage the voice hangout (channel call) state for a channel |
| `POST` | `https://discord.com/api/v9/channels/{id}/{id}/mod-report` | Submit a moderation report for a channel sub-resource (e.g. a message) |
| `PUT` | `https://discord.com/api/v9/conference-mode/channels/{id}` | Get a specific channel in conference mode |
| `GET` | `https://discord.com/api/v9/conference-mode/channels/{id}/users` | List users of a conference-mode channel |
| `PUT` | `https://discord.com/api/v9/conference-mode/conference` | Get the current conference-mode conference state |
| `GET` | `https://discord.com/api/v9/conference-mode/events` | List conference-mode events |
| `GET` | `https://discord.com/api/v9/conference-mode/guilds` | List guilds available in conference mode |
| `? (id-gated)` | `https://discord.com/api/v9/conference-mode/voice/{id}/{id}` | Access voice state for a conference-mode resource by nested IDs |
| `GET` | `https://discord.com/api/v9/conference-mode/{id}/channels` | List channels of a specific conference-mode resource |
| `GET` | `https://discord.com/api/v9/connections/{id}/authorize` | Begin authorization for a specific connection provider |
| `GET` | `https://discord.com/api/v9/connections/{id}/callback` | Handle the OAuth callback for a connection provider |
| `GET` | `https://discord.com/api/v9/connections/{id}/callback/session-handoff` | Handle a connection callback with session handoff to another device |
| `GET` | `https://discord.com/api/v9/connections/{id}/link` | Link an external account via a connection provider |
| `GET` | `https://discord.com/api/v9/connections/{id}/link-authorize` | Authorize linking an external account for a connection provider |
| `POST` | `https://discord.com/api/v9/connections/{id}/link-dispatch-auth-callback` | Dispatch the auth callback for a connection link flow |
| `POST` | `https://discord.com/api/v9/consoles/connect-request` | Create a request to connect a game console |
| `DELETE` | `https://discord.com/api/v9/consoles/connect-request/{id}` | Get the status of a specific console connect request |
| `GET` | `https://discord.com/api/v9/consoles/xbox-handoff` | Hand off a session to an Xbox console |
| `GET` | `https://discord.com/api/v9/consoles/{id}/devices` | List devices attached to a specific console |
| `POST` | `https://discord.com/api/v9/consoles/{id}/devices/{id}/commands` | Send or list commands for a specific console device |
| `DELETE` | `https://discord.com/api/v9/consoles/{id}/devices/{id}/commands/{id}` | Get the status of a specific command sent to a console device |
| `? (id-gated)` | `https://discord.com/api/v9/content-inventory/users/@me${null!=e?` | Fetch the current user's content inventory feed (dynamic query template) |
| `PATCH` | `https://discord.com/api/v9/content-inventory/users/@me/applications/{id}` | Get the current user's content inventory entries for a specific application |
| `DELETE` | `https://discord.com/api/v9/content-inventory/users/@me/outbox/entries/id/{id}/history` | Get the history of a specific content inventory outbox entry for the current user |
| `GET` | `https://discord.com/api/v9/content-inventory/users/@me/similar-games/{id}` | Get games similar to a given game for the current user |
| `POST` | `https://discord.com/api/v9/content-inventory/users/@me/spotify` | Get the current user's Spotify content inventory data |
| `GET` | `https://discord.com/api/v9/content-inventory/users/{id}/outbox` | Get the content inventory outbox of a specific user |
| `GET` | `https://discord.com/api/v9/discovery/categories` | List available discovery categories |
| `? (id-gated)` | `https://discord.com/api/v9/discovery/{id}` | Get a discovery surface/section by ID |
| `GET` | `https://discord.com/api/v9/family-center/@me` | Get the current user's Family Center profile/state |
| `GET` | `https://discord.com/api/v9/family-center/@me/link-code` | Generate/retrieve the current user's Family Center link code for pairing a parent/teen |
| `GET` | `https://discord.com/api/v9/family-center/more-activity/{id}/{id}/{id}/{id}` | Fetch additional Family Center activity records for linked accounts by nested IDs |
| `POST` | `https://discord.com/api/v9/family-center/share-iar-with-parents` | Toggle sharing of in-app-recent (activity) data with linked parents |
| `? (id-gated)` | `https://discord.com/api/v9/family-center/teen-user/{id}` | Get a linked teen user's Family Center record by user ID |
| `GET` | `https://discord.com/api/v9/family-center/{id}/activity` | Get a linked family member's recent activity by user ID |
| `PATCH` | `https://discord.com/api/v9/family-center/{id}/consents` | Get/update Family Center consents for a linked user by ID |
| `POST` | `https://discord.com/api/v9/family-center/{id}/restricted-schedule/rule` | Create a restricted-schedule (screen-time) rule for a linked user by ID |
| `PATCH,DELETE` | `https://discord.com/api/v9/family-center/{id}/restricted-schedule/rules/{id}` | Get/update/delete a specific restricted-schedule rule for a linked user by IDs |
| `GET` | `https://discord.com/api/v9/family-center/{id}/settings-and-consents` | Get combined settings and consents for a linked Family Center user by ID |
| `PATCH` | `https://discord.com/api/v9/family-center/{id}/settings-proto` | Get/update the protobuf-encoded Family Center settings for a linked user by ID |
| `GET` | `https://discord.com/api/v9/games` | List games (game store/library catalog) |
| `GET` | `https://discord.com/api/v9/games/detectable` | List games detectable by the client for rich-presence game detection |
| `GET` | `https://discord.com/api/v9/games/detectable/exclusions` | List excluded executables/processes for game detection |
| `GET` | `https://discord.com/api/v9/games/{id}` | Get a game's catalog details by game ID |
| `GET` | `https://discord.com/api/v9/games/{id}/announcements` | List announcements for a specific game by game ID |
| `GET` | `https://discord.com/api/v9/gifs/search` | Search GIFs (Tenor-backed GIF search) |
| `POST` | `https://discord.com/api/v9/gifs/select` | Record selection of a GIF (analytics/usage signal for GIF picker) |
| `GET` | `https://discord.com/api/v9/gifs/suggest` | Get suggested GIF search terms/categories |
| `GET` | `https://discord.com/api/v9/gifs/trending` | List trending GIFs |
| `GET` | `https://discord.com/api/v9/gifs/trending-gifs` | List trending GIF media items |
| `GET` | `https://discord.com/api/v9/gifs/trending-search` | List trending GIF search terms |
| `POST` | `https://discord.com/api/v9/guilds` | Create a new guild (POST) / base guilds collection endpoint |
| `POST` | `https://discord.com/api/v9/guilds/automations/email-domain-lookup` | Look up a guild automation email-domain (member-verification via corporate email domain) |
| `POST` | `https://discord.com/api/v9/guilds/automations/email-domain-lookup/verify` | Initiate verification of a guild automation email domain |
| `POST` | `https://discord.com/api/v9/guilds/automations/email-domain-lookup/verify-code` | Submit the verification code to confirm a guild automation email domain |
| `GET` | `https://discord.com/api/v9/guilds/create` | Create a new guild |
| `GET` | `https://discord.com/api/v9/guilds/gravity-join` | Join a guild surfaced/recommended through the Gravity engine |
| `? (id-gated)` | `https://discord.com/api/v9/guilds/settings${null!=e?` | Fetch/update cross-guild settings (template-built URL with optional query suffix) |
| `POST` | `https://discord.com/api/v9/guilds/{id}/ack/{id}/{id}` | Acknowledge (mark read) a message in a channel of a guild |
| `GET` | `https://discord.com/api/v9/guilds/{id}/active-channels` | List the currently active channels in a guild |
| `GET` | `https://discord.com/api/v9/guilds/{id}/admin-server-eligibility` | Check the guild's eligibility to become/join an admin (community moderator) server |
| `GET` | `https://discord.com/api/v9/guilds/{id}/analytics/engagement/overview` | Get engagement analytics overview for a guild |
| `GET` | `https://discord.com/api/v9/guilds/{id}/analytics/growth-activation/overview` | Get growth/activation analytics overview for a guild |
| `GET` | `https://discord.com/api/v9/guilds/{id}/analytics/growth-activation/retention` | Get growth/activation retention analytics for a guild |
| `GET` | `https://discord.com/api/v9/guilds/{id}/application-command-index` | Fetch the index of application (slash) commands available in a guild |
| `GET` | `https://discord.com/api/v9/guilds/{id}/application-commands/{id}` | Get a specific application command in a guild |
| `GET` | `https://discord.com/api/v9/guilds/{id}/applications` | List applications/integrations associated with a guild |
| `POST` | `https://discord.com/api/v9/guilds/{id}/auto-moderation/alert-action` | Take an action on an AutoMod alert in a guild |
| `POST` | `https://discord.com/api/v9/guilds/{id}/auto-moderation/clear-mention-raid` | Clear an active mention-raid AutoMod state for a guild |
| `POST` | `https://discord.com/api/v9/guilds/{id}/auto-moderation/false-alarm` | Report an AutoMod alert as a false alarm in a guild |
| `POST` | `https://discord.com/api/v9/guilds/{id}/auto-moderation/report-raid` | Report a raid to AutoMod for a guild |
| `GET` | `https://discord.com/api/v9/guilds/{id}/auto-moderation/rules/validate` | Validate a proposed AutoMod rule configuration for a guild |
| `GET` | `https://discord.com/api/v9/guilds/{id}/bans/search` | Search the bans of a guild |
| `GET` | `https://discord.com/api/v9/guilds/{id}/basic` | Fetch basic/minimal metadata for a guild |
| `POST` | `https://discord.com/api/v9/guilds/{id}/creator-monetization/accept-new-terms-demonetized` | Accept updated creator-monetization terms after demonetization for a guild |
| `POST` | `https://discord.com/api/v9/guilds/{id}/creator-monetization/accept-terms` | Accept the initial creator-monetization terms for a guild |
| `POST` | `https://discord.com/api/v9/guilds/{id}/creator-monetization/enable-requests` | Submit/list requests to enable creator monetization for a guild |
| `POST` | `https://discord.com/api/v9/guilds/{id}/creator-monetization/enable-requests/{id}/accept-terms` | Accept terms for a specific creator-monetization enable request in a guild |
| `GET` | `https://discord.com/api/v9/guilds/{id}/creator-monetization/marketing/onboarding` | Run the creator-monetization marketing onboarding flow for a guild |
| `POST` | `https://discord.com/api/v9/guilds/{id}/creator-monetization/ownership-transfer/onboarding` | Run the creator-monetization ownership-transfer onboarding flow for a guild |
| `POST` | `https://discord.com/api/v9/guilds/{id}/creator-monetization/remove-monetization` | Remove/disable creator monetization for a guild |
| `GET` | `https://discord.com/api/v9/guilds/{id}/creator-monetization/requirements` | Get the creator-monetization eligibility requirements for a guild |
| `GET` | `https://discord.com/api/v9/guilds/{id}/creator-monetization/restrictions` | Get creator-monetization restrictions applied to a guild |
| `POST` | `https://discord.com/api/v9/guilds/{id}/delete` | Delete a guild |
| `GET` | `https://discord.com/api/v9/guilds/{id}/directory-entries/broadcast` | Broadcast/list student-hub directory entries for a guild |
| `POST,PUT,DELETE` | `https://discord.com/api/v9/guilds/{id}/discovery-categories/{id}` | Add or remove a specific discovery category for a guild |
| `GET` | `https://discord.com/api/v9/guilds/{id}/discovery-metadata` | Get or update the discovery metadata for a guild |
| `GET` | `https://discord.com/api/v9/guilds/{id}/discovery-requirements` | Get the discovery requirements/eligibility status for a guild |
| `GET` | `https://discord.com/api/v9/guilds/{id}/entitlements` | List entitlements (purchases/grants) for a guild |
| `PATCH` | `https://discord.com/api/v9/guilds/{id}/entitlements/{id}` | Get a specific entitlement for a guild |
| `GET` | `https://discord.com/api/v9/guilds/{id}/game-server-regions` | List available game-server regions for a guild |
| `GET` | `https://discord.com/api/v9/guilds/{id}/game-servers` | List or manage hosted game servers for a guild |
| `POST` | `https://discord.com/api/v9/guilds/{id}/game-servers/{id}/wake` | Wake (start) a specific hosted game server in a guild |
| `GET` | `https://discord.com/api/v9/guilds/{id}/guild-feed` | Fetch the guild activity feed |
| `PUT` | `https://discord.com/api/v9/guilds/{id}/incident-actions` | Configure/trigger incident (safety-alert) actions for a guild |
| `POST` | `https://discord.com/api/v9/guilds/{id}/integrations/{id}/sync` | Force-sync a specific integration in a guild |
| `POST` | `https://discord.com/api/v9/guilds/{id}/join-admin-server` | Join the admin (community moderator) server associated with a guild |
| `GET` | `https://discord.com/api/v9/guilds/{id}/member-verification` | Get or update the membership-verification (gate) screening form for a guild |
| `POST` | `https://discord.com/api/v9/guilds/{id}/members-search` | Search the members of a guild (advanced member search) |
| `GET` | `https://discord.com/api/v9/guilds/{id}/members/supplemental` | Fetch supplemental member data for a guild |
| `GET` | `https://discord.com/api/v9/guilds/{id}/members/unusual-dm-activity` | List members flagged for unusual DM activity in a guild |
| `GET` | `https://discord.com/api/v9/guilds/{id}/messages/official` | Fetch official/system messages for a guild |
| `POST` | `https://discord.com/api/v9/guilds/{id}/messages/search/tabs` | Fetch the search-result tabs/facets for a guild message search |
| `POST` | `https://discord.com/api/v9/guilds/{id}/mfa` | Get or set the multi-factor-authentication (2FA) requirement level for a guild |
| `POST` | `https://discord.com/api/v9/guilds/{id}/migrate-bypass-slowmode-permission` | Migrate the guild's roles to the new bypass-slowmode permission |
| `POST` | `https://discord.com/api/v9/guilds/{id}/migrate-command-scope` | Migrate the guild to the new applications.commands authorization scope |
| `POST` | `https://discord.com/api/v9/guilds/{id}/migrate-pin-permission` | Migrate the guild's roles to the new pin-messages permission |
| `POST` | `https://discord.com/api/v9/guilds/{id}/new-member-action/{id}` | Get or complete a specific new-member action (singular) in a guild |
| `GET` | `https://discord.com/api/v9/guilds/{id}/new-member-actions` | List the configured new-member onboarding actions for a guild |
| `PATCH` | `https://discord.com/api/v9/guilds/{id}/new-member-actions/{id}` | Get, modify, or complete a specific new-member action in a guild |
| `DELETE` | `https://discord.com/api/v9/guilds/{id}/onboarding-prompts/{id}` | Get or modify a specific onboarding prompt in a guild |
| `POST,PUT` | `https://discord.com/api/v9/guilds/{id}/onboarding-responses` | Submit/list a member's answers to the guild's onboarding prompt questions |
| `GET` | `https://discord.com/api/v9/guilds/{id}/onboarding/allowed-applications` | List/manage applications allowed to surface during the guild's onboarding flow |
| `PUT` | `https://discord.com/api/v9/guilds/{id}/pincode` | Get/set the guild's PIN code (e.g. junior/age-gated or staff access PIN) |
| `GET` | `https://discord.com/api/v9/guilds/{id}/powerups` | List/manage Server Power-ups (boost-like perk consumables) applied to the guild |
| `GET` | `https://discord.com/api/v9/guilds/{id}/premium/subscriptions` | List/create premium subscriptions backing the guild's boosts |
| `DELETE` | `https://discord.com/api/v9/guilds/{id}/premium/subscriptions/{id}` | Get/update/delete a specific premium (boost) subscription on the guild |
| `POST` | `https://discord.com/api/v9/guilds/{id}/products` | List the guild's monetization products (server shop items) |
| `POST` | `https://discord.com/api/v9/guilds/{id}/products/attachments` | Upload/list media attachments associated with the guild's products |
| `? (id-gated)` | `https://discord.com/api/v9/guilds/{id}/products/listings${null!=t?` | List the guild's product listings (storefront-facing offerings; bundle string fragment) |
| `POST` | `https://discord.com/api/v9/guilds/{id}/products/listings/{id}/attachments/{id}/download` | Download a specific attachment file from a guild product listing |
| `GET` | `https://discord.com/api/v9/guilds/{id}/profile` | Get/update the guild's discovery/profile object (description, tags, badges) |
| `PUT` | `https://discord.com/api/v9/guilds/{id}/profile/visibility` | Get/set the visibility of the current user's membership on the guild's member profile |
| `GET` | `https://discord.com/api/v9/guilds/{id}/prune/v2` | Version-2 endpoint to preview/execute pruning of inactive guild members |
| `GET` | `https://discord.com/api/v9/guilds/{id}/requests/@me` | Get or submit the current user's own join request for the guild |
| `GET` | `https://discord.com/api/v9/guilds/{id}/requests/users/{id}` | Get the join request submitted by a specific user for the guild |
| `POST,PATCH` | `https://discord.com/api/v9/guilds/{id}/requests/{id}/ack` | Acknowledge (mark seen) a specific guild join request |
| `PUT` | `https://discord.com/api/v9/guilds/{id}/resource-channels/{id}` | Get/manage a specific onboarding resource channel highlighted to new members |
| `? (id-gated)` | `https://discord.com/api/v9/guilds/{id}/role-subscriptions/group-listings${null!=t?` | List the guild's role-subscription group listings (subscription tier groups; bundle string fragment) |
| `? (id-gated)` | `https://discord.com/api/v9/guilds/{id}/role-subscriptions/group-listings/{id}/subscription-listings${null!=n?` | List subscription listings within a specific role-subscription group (bundle string fragment) |
| `POST` | `https://discord.com/api/v9/guilds/{id}/role-subscriptions/group-listings/{id}/subscription-listings/{id}/archive` | Archive a specific subscription listing within a role-subscription group |
| `GET` | `https://discord.com/api/v9/guilds/{id}/role-subscriptions/settings` | Get/update the guild's role-subscription program settings |
| `PATCH` | `https://discord.com/api/v9/guilds/{id}/role-subscriptions/subscription-listings/{id}/trial` | Get/create the free-trial configuration for a role-subscription listing |
| `GET` | `https://discord.com/api/v9/guilds/{id}/role-subscriptions/subscription-listings/{id}/trial/{id}/eligibility` | Check the current user's eligibility for a specific role-subscription trial |
| `GET` | `https://discord.com/api/v9/guilds/{id}/role-subscriptions/templates` | List/manage reusable templates for the guild's role-subscription tiers |
| `GET` | `https://discord.com/api/v9/guilds/{id}/role-subscriptions/trials` | List the guild's role-subscription trials |
| `GET` | `https://discord.com/api/v9/guilds/{id}/roles/connections-configurations` | List linked-role connection configurations defined for the guild |
| `POST` | `https://discord.com/api/v9/guilds/{id}/roles/{id}/connections/assign` | Assign a linked-role connection requirement to a specific role |
| `GET` | `https://discord.com/api/v9/guilds/{id}/roles/{id}/connections/configuration` | Get/update the linked-role connection requirements for a specific role |
| `GET` | `https://discord.com/api/v9/guilds/{id}/roles/{id}/connections/eligibility` | Check the current user's eligibility to receive a linked role via connections |
| `POST` | `https://discord.com/api/v9/guilds/{id}/roles/{id}/connections/unassign` | Remove a linked-role connection requirement from a specific role |
| `GET` | `https://discord.com/api/v9/guilds/{id}/roles/{id}/member-ids` | List the user IDs of all members holding a specific role |
| `PATCH` | `https://discord.com/api/v9/guilds/{id}/roles/{id}/members` | List/add members holding a specific role |
| `? (id-gated)` | `https://discord.com/api/v9/guilds/{id}/scheduled-events/{id}${null!=n?` | Get/update a specific scheduled event (with query options; bundle string fragment) |
| `POST` | `https://discord.com/api/v9/guilds/{id}/scheduled-events/{id}/exceptions` | List/create recurrence exceptions (skipped/modified occurrences) for a scheduled event |
| `PATCH,DELETE` | `https://discord.com/api/v9/guilds/{id}/scheduled-events/{id}/exceptions/{id}` | Get/update/delete a specific recurrence exception of a scheduled event |
| `GET` | `https://discord.com/api/v9/guilds/{id}/scheduled-events/{id}/users/counts` | Get the count of users interested in/RSVP'd to a scheduled event |
| `? (id-gated)` | `https://discord.com/api/v9/guilds/{id}/settings${null!=t?` | Get/update the guild's settings object (bundle string fragment) |
| `POST,DELETE` | `https://discord.com/api/v9/guilds/{id}/skus/{id}` | Get a specific SKU (purchasable item) associated with the guild |
| `GET` | `https://discord.com/api/v9/guilds/{id}/top-emojis` | Get the guild's most-used custom emojis |
| `GET` | `https://discord.com/api/v9/guilds/{id}/top-games` | Get the games most played by the guild's members |
| `GET` | `https://discord.com/api/v9/guilds/{id}/top-read-channels` | Get the guild's most-read channels for the current user |
| `GET` | `https://discord.com/api/v9/guilds/{id}/voice-hangout/recent-images` | List recent images shared in the guild's voice hangout/channel |
| `GET` | `https://discord.com/api/v9/haven/assets` | List static assets for the Haven (family-center/teen-safety) feature |
| `POST` | `https://discord.com/api/v9/haven/{id}/connect` | Connect/link an account to a specific Haven (family center) relationship |
| `POST` | `https://discord.com/api/v9/haven/{id}/disconnect` | Disconnect/unlink an account from a specific Haven relationship |
| `POST` | `https://discord.com/api/v9/haven/{id}/update` | Update settings/permissions for a specific Haven relationship |
| `? (id-gated)` | `https://discord.com/api/v9/hc/{id}` | Fetch a Help Center locale/section root page |
| `? (id-gated)` | `https://discord.com/api/v9/hc/{id}/articles/{id}` | Fetch a specific Help Center article by ID |
| `? (id-gated)` | `https://discord.com/api/v9/hc/{id}/requests/new?platform={id}` | Open a new Help Center support request form for the given platform |
| `? (id-gated)` | `https://discord.com/api/v9/hc/{id}/search?utf8=%E2%9C%93&query={id}&commit=Search` | Search Help Center articles for the given query |
| `POST` | `https://discord.com/api/v9/oauth2/account-linking-achievement` | OAuth2 flow for linking an external game account to grant an achievement |
| `POST` | `https://discord.com/api/v9/oauth2/allowlist/accept` | Accept an OAuth2 application allowlist invitation for a restricted/unverified app |
| `GET` | `https://discord.com/api/v9/oauth2/applications/{id}/assets` | List or upload visual assets (icons/rich-presence art) for an OAuth2 application |
| `GET` | `https://discord.com/api/v9/oauth2/applications/{id}/rpc` | Get or manage the RPC/local-client config for an OAuth2 application |
| `GET` | `https://discord.com/api/v9/oauth2/authorize` | OAuth2 authorization endpoint where the user grants scopes to an application |
| `GET` | `https://discord.com/api/v9/oauth2/authorize/webhook-channels` | List channels eligible as webhook targets during an incoming-webhook OAuth2 authorization |
| `POST` | `https://discord.com/api/v9/oauth2/device/finish` | Complete the OAuth2 device-authorization-grant flow after user approval |
| `POST` | `https://discord.com/api/v9/oauth2/device/verify` | Verify the user-code in the OAuth2 device-authorization (TV/console login) flow |
| `GET` | `https://discord.com/api/v9/oauth2/samsung/authorize` | Initiate the Samsung partner OAuth2 authorization flow |
| `GET` | `https://discord.com/api/v9/oauth2/samsung/authorize/callback` | Handle the Samsung partner OAuth2 authorization callback/redirect |
| `GET` | `https://discord.com/api/v9/oauth2/tokens` | List the current user's active OAuth2 access tokens/grants |
| `GET` | `https://discord.com/api/v9/oauth2/tokens/{id}` | Get or revoke a specific OAuth2 token/grant by its ID |
| `GET` | `https://discord.com/api/v9/partner-sdk/applications/{id}/application-storefront` | Get the partner-SDK application storefront config for an application by ID |
| `GET` | `https://discord.com/api/v9/partner-sdk/applications/{id}/storefront/skus/{id}` | Get a specific SKU in a partner-SDK application's storefront (application ID then SKU ID) |
| `GET` | `https://discord.com/api/v9/partner-sdk/guilds/{id}/application-storefront` | Get the partner-SDK application storefront attached to a guild by ID |
| `GET` | `https://discord.com/api/v9/partner-sdk/guilds/{id}/application-storefront/announcement` | Get or post the storefront announcement for a guild's partner-SDK application storefront |
| `GET` | `https://discord.com/api/v9/partner-sdk/guilds/{id}/application-storefront/skus/{id}` | Get a specific SKU in a guild's partner-SDK application storefront (guild ID then SKU ID) |
| `POST` | `https://discord.com/api/v9/partner-sdk/guilds/{id}/application-storefront/skus/{id}/eligibility` | Check the current user's purchase/access eligibility for a guild storefront SKU |
| `GET` | `https://discord.com/api/v9/partner-sdk/storefront-config` | Get the global partner-SDK storefront configuration |
| `GET` | `https://discord.com/api/v9/partner-sdk/storefront-eligibility` | Check the current user's eligibility for the partner-SDK storefront |
| `GET` | `https://discord.com/api/v9/quests/@me` | List the current user's Quests (enrolled/available state) |
| `GET` | `https://discord.com/api/v9/quests/@me/claimed` | List Quests the current user has already claimed rewards for |
| `POST` | `https://discord.com/api/v9/quests/creatives/{id}/claim-reward` | Claim the reward for a Quest creative/ad unit by its ID |
| `GET` | `https://discord.com/api/v9/quests/decision` | Submit/fetch the current user's Quest targeting decision |
| `GET` | `https://discord.com/api/v9/quests/earned-decision` | Fetch the decision on which earned Quest reward to surface |
| `GET` | `https://discord.com/api/v9/quests/get-decisions` | Retrieve Quest eligibility/targeting decisions for the user |
| `GET` | `https://discord.com/api/v9/quests/preview` | Fetch a generic Quest preview payload |
| `GET` | `https://discord.com/api/v9/quests/reset-recent-quest-completions` | Reset the user's recent Quest completion records (test/internal) |
| `GET` | `https://discord.com/api/v9/quests/{id}` | Fetch a specific Quest by its quest ID |
| `POST` | `https://discord.com/api/v9/quests/{id}/claim-reward` | Claim the reward for a completed Quest by quest ID |
| `POST` | `https://discord.com/api/v9/quests/{id}/console/start` | Mark a console-platform Quest as started for the user |
| `POST` | `https://discord.com/api/v9/quests/{id}/console/stop` | Mark a console-platform Quest as stopped for the user |
| `POST` | `https://discord.com/api/v9/quests/{id}/dismissible-content/{id}/dismiss` | Dismiss a piece of dismissible content tied to a Quest |
| `POST` | `https://discord.com/api/v9/quests/{id}/enroll` | Enroll the current user into the specified Quest |
| `POST` | `https://discord.com/api/v9/quests/{id}/heartbeat` | Send a progress heartbeat for an in-progress Quest task |
| `GET` | `https://discord.com/api/v9/quests/{id}/preview` | Fetch the preview payload for a specific Quest |
| `POST` | `https://discord.com/api/v9/quests/{id}/preview/complete` | Mark a Quest preview as completed (preview/test flow) |
| `DELETE` | `https://discord.com/api/v9/quests/{id}/preview/dismissibility` | Fetch dismissibility state for a Quest preview |
| `DELETE` | `https://discord.com/api/v9/quests/{id}/preview/status` | Fetch the status of a Quest preview |
| `GET` | `https://discord.com/api/v9/quests/{id}/reward-code` | Retrieve the redeemable reward code earned for a Quest |
| `POST` | `https://discord.com/api/v9/quests/{id}/video-progress` | Report video-watch progress toward a video-watch Quest |
| `GET` | `https://discord.com/api/v9/reporting/menu/{id}` | Fetch the reporting flow menu node by its ID |
| `POST` | `https://discord.com/api/v9/reporting/review` | Review a submission within the reporting flow |
| `GET` | `https://discord.com/api/v9/reporting/unauthenticated/capabilities` | Fetch reporting capabilities available to unauthenticated reporters |
| `GET` | `https://discord.com/api/v9/reporting/unauthenticated/experiment` | Fetch experiment assignment for the unauthenticated reporting flow |
| `GET` | `https://discord.com/api/v9/reporting/unauthenticated/menu/{id}` | Fetch an unauthenticated reporting flow menu node by ID |
| `POST` | `https://discord.com/api/v9/reporting/unauthenticated/{id}` | Fetch an unauthenticated report record by its ID |
| `POST` | `https://discord.com/api/v9/reporting/unauthenticated/{id}/code` | Request a verification code for an unauthenticated report |
| `POST` | `https://discord.com/api/v9/reporting/unauthenticated/{id}/verify` | Verify an unauthenticated report via emailed code |
| `POST` | `https://discord.com/api/v9/reporting/{id}` | Fetch a reporting flow record/node by its ID |
| `GET` | `https://discord.com/api/v9/safety-hub/@me` | Fetch the current user's Safety Hub status/records |
| `PUT` | `https://discord.com/api/v9/safety-hub/request-review/{id}` | Request a review of a Safety Hub action by its case ID |
| `POST` | `https://discord.com/api/v9/safety-hub/suspended/@me` | Fetch the current user's account-suspension details |
| `POST` | `https://discord.com/api/v9/safety-hub/suspended/check-verification` | Check verification status during a suspension appeal |
| `PUT` | `https://discord.com/api/v9/safety-hub/suspended/request-review/{id}` | Request review of a suspension case by its ID |
| `POST` | `https://discord.com/api/v9/safety-hub/suspended/request-verification` | Request identity verification to appeal a suspension |
| `? (id-gated)` | `https://discord.com/api/v9/settings/changelogs${null!=e?` | Client route for settings changelogs (templated URL fragment) |
| `? (id-gated)` | `https://discord.com/api/v9/settings/{id}${null!=t?` | Client route for a specific settings section by ID (templated fragment) |
| `GET` | `https://discord.com/api/v9/shop/search` | Search the Discord Shop catalog |
| `? (id-gated)` | `https://discord.com/api/v9/store/applications/{id}${null!=t?` | Fetch store data for an application by ID (templated URL fragment) |
| `DELETE` | `https://discord.com/api/v9/store/applications/{id}/assets/{id}.{id}` | Fetch a store asset image for an application by app ID and asset hash |
| `GET` | `https://discord.com/api/v9/store/directory-layouts/{id}` | Fetch a store directory layout by its ID |
| `GET` | `https://discord.com/api/v9/store/directory/{id}` | Fetch a store directory category by its ID |
| `POST` | `https://discord.com/api/v9/store/email/resend-payment-verification` | Resend the payment verification email for a store purchase |
| `GET` | `https://discord.com/api/v9/store/eulas/{id}` | Fetch a store EULA (end-user license agreement) by its ID |
| `GET` | `https://discord.com/api/v9/store/listings/{id}` | Fetch a store SKU listing by its ID |
| `GET` | `https://discord.com/api/v9/store/price-tiers` | List Nitro/store price tiers |
| `GET` | `https://discord.com/api/v9/store/published-listings/applications` | List published store listings for applications (premium apps/games available in the store) |
| `GET` | `https://discord.com/api/v9/store/published-listings/applications/{id}` | Get a specific application's published store listing by listing ID |
| `GET` | `https://discord.com/api/v9/store/published-listings/skus` | List published store listings for SKUs (sellable products) |
| `GET` | `https://discord.com/api/v9/store/published-listings/skus/{id}` | Get a specific SKU's published store listing by listing ID |
| `GET` | `https://discord.com/api/v9/store/published-listings/skus/{id}/subscription-plans` | List the subscription plans available for a published SKU listing |
| `GET` | `https://discord.com/api/v9/store/skus/{id}` | Get a store SKU (sellable product) by its SKU ID |
| `? (id-gated)` | `https://discord.com/api/v9/store/skus/{id}${null!=t?` | Get a store SKU by ID (client URL-template artifact; resolves to /store/skus/{id} with optional query) |
| `GET` | `https://discord.com/api/v9/store/skus/{id}/listings` | List the store listings associated with a given SKU |
| `GET` | `https://discord.com/api/v9/store/skus/{id}/purchase` | Purchase the given SKU (initiate a store purchase for the current user) |
| `GET` | `https://discord.com/api/v9/storefront/collections` | List storefront collections (curated groupings of store products) |
| `GET` | `https://discord.com/api/v9/storefront/collections/applications` | List applications featured in storefront collections |
| `GET` | `https://discord.com/api/v9/storefront/collections/{id}` | Get a specific storefront collection by ID |
| `GET` | `https://discord.com/api/v9/storefront/pricing` | Get storefront pricing information (localized prices for store products) |
| `GET` | `https://discord.com/api/v9/storefront/products` | List storefront products available for sale |
| `GET` | `https://discord.com/api/v9/storefront/products/sku/{id}` | Get the storefront product associated with a given SKU ID |
| `GET` | `https://discord.com/api/v9/storefront/products/skus` | List storefront products by their SKUs |
| `GET` | `https://discord.com/api/v9/storefront/promotions` | List active storefront promotions/offers |
| `POST` | `https://discord.com/api/v9/streams/{id}/notify` | Send a Go-Live stream notification to followers/viewers for the given stream |
| `GET` | `https://discord.com/api/v9/streams/{id}/preview` | Get a preview thumbnail for the given Go-Live stream |
| `PATCH` | `https://discord.com/api/v9/streams/{id}/stream` | Manage/control the given Go-Live stream session |
| `? (id-gated)` | `https://discord.com/api/v9/user-offers/create/{id}/{id}` | Create/claim a user offer by offer type ID and offer ID for the current user |
| `? (id-gated)` | `https://discord.com/api/v9/user-offers/{id}/{id}` | Get/act on a specific user offer by offer type ID and offer ID |
| `GET` | `https://discord.com/api/v9/users/@me/activities/statistics/applications` | Get the current user's per-application activity/playtime statistics |
| `POST` | `https://discord.com/api/v9/users/@me/activities/subscribe` | Subscribe the current user to activity updates (rich-presence activity feed) |
| `GET` | `https://discord.com/api/v9/users/@me/affinities/channels` | Get the current user's channel affinities (algorithmically ranked channels) |
| `GET` | `https://discord.com/api/v9/users/@me/affinities/guilds` | Get the current user's guild affinities (algorithmically ranked servers) |
| `GET` | `https://discord.com/api/v9/users/@me/affinities/users` | Get the current user's user affinities (algorithmically ranked contacts) |
| `GET` | `https://discord.com/api/v9/users/@me/affinities/v2/channels` | Get the current user's channel affinities (v2 ranking algorithm) |
| `GET` | `https://discord.com/api/v9/users/@me/affinities/v2/users` | Get the current user's user affinities (v2 ranking algorithm) |
| `GET` | `https://discord.com/api/v9/users/@me/age-verification/check` | Check the current user's age-verification status |
| `POST` | `https://discord.com/api/v9/users/@me/age-verification/reset` | Reset the current user's age-verification state |
| `PATCH` | `https://discord.com/api/v9/users/@me/agreements` | Get or accept the current user's legal agreements (ToS/Privacy acceptance) |
| `GET` | `https://discord.com/api/v9/users/@me/application-command-index` | Get the current user's application command index (slash-command autocomplete catalog) |
| `PATCH` | `https://discord.com/api/v9/users/@me/application-identities/{id}/{id}/config` | Get/update the current user's application-identity config for a given app and identity |
| `GET` | `https://discord.com/api/v9/users/@me/applications/role-connections` | List the current user's linked-role connections across applications |
| `POST` | `https://discord.com/api/v9/users/@me/applications/{id}/entitlement-ticket` | Get an entitlement ticket for the given application for the current user |
| `POST` | `https://discord.com/api/v9/users/@me/applications/{id}/ticket` | Get an app ticket for the given application for the current user (game/app launch ticket) |
| `GET` | `https://discord.com/api/v9/users/@me/avatars` | List the current user's saved avatars (avatar decorations/profile avatars) |
| `DELETE` | `https://discord.com/api/v9/users/@me/avatars/{id}` | Get/manage a specific saved avatar by ID for the current user |
| `POST` | `https://discord.com/api/v9/users/@me/background-sync` | Trigger the current user's background data sync |
| `GET` | `https://discord.com/api/v9/users/@me/billing/adyen/payment-methods` | List the current user's Adyen payment methods |
| `POST` | `https://discord.com/api/v9/users/@me/billing/apple/trial-offer-signature` | Get a signed Apple trial-offer signature for the current user's in-app purchase |
| `GET` | `https://discord.com/api/v9/users/@me/billing/campaign-context` | Get billing campaign context for the current user (promo/marketing campaign targeting) |
| `GET` | `https://discord.com/api/v9/users/@me/billing/checkout-recovery` | Get checkout-recovery state for the current user (resume an abandoned checkout) |
| `GET` | `https://discord.com/api/v9/users/@me/billing/churn-user-offer` | Get a churn-prevention retention offer for the current user |
| `GET` | `https://discord.com/api/v9/users/@me/billing/country-code` | Get the billing country code detected for the current user |
| `GET` | `https://discord.com/api/v9/users/@me/billing/eligible-application-subscription-guilds` | List guilds eligible for application/premium subscriptions for the current user |
| `POST` | `https://discord.com/api/v9/users/@me/billing/invoice` | Get/preview the current user's billing invoice |
| `GET` | `https://discord.com/api/v9/users/@me/billing/invoice/breakdown` | Get an itemized breakdown of the current user's billing invoice |
| `GET` | `https://discord.com/api/v9/users/@me/billing/localized-pricing-promo` | Get localized pricing and promotion details for the current user |
| `GET` | `https://discord.com/api/v9/users/@me/billing/location-info` | Get the current user's billing location info (region/tax data) |
| `GET` | `https://discord.com/api/v9/users/@me/billing/nitro-affinity` | Get the current user's Nitro affinity (propensity-to-subscribe signal) |
| `GET` | `https://discord.com/api/v9/users/@me/billing/payment-source-creation-context` | Get context needed to create a new payment source for the current user |
| `GET` | `https://discord.com/api/v9/users/@me/billing/payment-sources` | List the current user's payment sources (saved cards/PayPal) |
| `GET` | `https://discord.com/api/v9/users/@me/billing/payment-sources/validate-billing-address` | Validate a billing address for the current user's payment source |
| `GET` | `https://discord.com/api/v9/users/@me/billing/payment-sources/{id}` | Get/update/delete a specific payment source by ID for the current user |
| `GET` | `https://discord.com/api/v9/users/@me/billing/payments` | List the current user's payment/transaction history |
| `GET` | `https://discord.com/api/v9/users/@me/billing/payments/{id}` | Get a specific payment/transaction by ID for the current user |
| `POST` | `https://discord.com/api/v9/users/@me/billing/payments/{id}/void` | Void a specific payment/transaction by ID for the current user |
| `POST` | `https://discord.com/api/v9/users/@me/billing/paypal/billing-agreement-tokens` | Create/get PayPal billing-agreement tokens for the current user |
| `GET` | `https://discord.com/api/v9/users/@me/billing/perks-relevance` | Get the relevance/eligibility of premium perks for the current user |
| `POST` | `https://discord.com/api/v9/users/@me/billing/stripe/payment-elements/setup-intents` | Create a Stripe Payment Elements setup intent for the current user's billing |
| `GET` | `https://discord.com/api/v9/users/@me/billing/stripe/payment-intents/payments/{id}` | Get a specific Stripe payment intent for a payment by ID for the current user's billing |
| `POST` | `https://discord.com/api/v9/users/@me/billing/stripe/setup-intents` | Create a Stripe setup intent to attach a payment method for the current user |
| `GET` | `https://discord.com/api/v9/users/@me/billing/subscriptions` | List or create the current user's premium (Nitro) billing subscriptions |
| `GET` | `https://discord.com/api/v9/users/@me/billing/subscriptions/preview` | Preview pricing/proration for a prospective subscription change before committing |
| `GET` | `https://discord.com/api/v9/users/@me/billing/subscriptions/{id}` | Fetch, modify, or cancel a specific billing subscription of the current user |
| `GET` | `https://discord.com/api/v9/users/@me/billing/subscriptions/{id}/eligible-users` | List users eligible to receive/share a slot of the given subscription |
| `POST` | `https://discord.com/api/v9/users/@me/billing/subscriptions/{id}/invites` | Manage invites to share the given subscription with other users |
| `GET` | `https://discord.com/api/v9/users/@me/billing/subscriptions/{id}/invoices` | List invoices generated for the given subscription |
| `POST` | `https://discord.com/api/v9/users/@me/billing/subscriptions/{id}/invoices/{id}/pay` | Pay a specific outstanding invoice on the given subscription |
| `GET` | `https://discord.com/api/v9/users/@me/billing/subscriptions/{id}/members` | List members occupying slots of the given (shared) subscription |
| `DELETE` | `https://discord.com/api/v9/users/@me/billing/subscriptions/{id}/members/{id}` | Fetch or remove a specific member from the given shared subscription |
| `PATCH,DELETE` | `https://discord.com/api/v9/users/@me/billing/subscriptions/{id}/members/{id}/invite` | Send/resend a slot invite to a specific member of the subscription |
| `GET` | `https://discord.com/api/v9/users/@me/billing/subscriptions/{id}/preview` | Preview pricing/proration for changes to this specific subscription |
| `POST` | `https://discord.com/api/v9/users/@me/billing/user-offer` | Fetch the current personalized billing/discount offer for the user |
| `POST` | `https://discord.com/api/v9/users/@me/billing/user-offer/ack` | Acknowledge (mark seen) the current user's billing offer |
| `POST` | `https://discord.com/api/v9/users/@me/billing/user-offer/redeem` | Redeem the current user's available billing offer |
| `GET` | `https://discord.com/api/v9/users/@me/billing/user-trial-offer` | Fetch the current user's available premium trial offer |
| `POST` | `https://discord.com/api/v9/users/@me/billing/user-trial-offer/{id}/ack` | Acknowledge (mark seen) a specific trial offer for the user |
| `GET` | `https://discord.com/api/v9/users/@me/billing/wallet/{id}/information` | Retrieve information for a specific wallet/payment source of the user |
| `POST` | `https://discord.com/api/v9/users/@me/captcha/verify` | Submit a CAPTCHA solution for verification by the current user |
| `POST` | `https://discord.com/api/v9/users/@me/channels/group-dm-shell` | Create an empty group-DM shell channel for the current user |
| `PUT` | `https://discord.com/api/v9/users/@me/claim-premium-collectibles-product` | Claim a premium collectibles product entitlement for the current user |
| `PUT` | `https://discord.com/api/v9/users/@me/clan` | Get or update the current user's clan (guild tag) affiliation |
| `GET` | `https://discord.com/api/v9/users/@me/collectibles-marketing` | Fetch collectibles marketing/promotional content for the current user |
| `GET` | `https://discord.com/api/v9/users/@me/collectibles-purchases` | List the current user's collectibles purchases |
| `PUT` | `https://discord.com/api/v9/users/@me/connections/contacts/@me/external-friend-list-entries` | List the current user's external (contact-synced) friend list entries |
| `PUT,PATCH,DELETE` | `https://discord.com/api/v9/users/@me/connections/{id}/{id}` | Fetch, update, or delete a specific third-party connection (by type and account ID) |
| `GET` | `https://discord.com/api/v9/users/@me/connections/{id}/{id}/access-token` | Retrieve the access token for a specific third-party connection |
| `POST` | `https://discord.com/api/v9/users/@me/connections/{id}/{id}/refresh` | Refresh the data/token of a specific third-party connection |
| `GET` | `https://discord.com/api/v9/users/@me/consent` | Get or update the current user's privacy/data-usage consent settings |
| `GET` | `https://discord.com/api/v9/users/@me/custom-themes` | List or manage the current user's custom client themes |
| `POST` | `https://discord.com/api/v9/users/@me/delete` | Permanently delete the current user's account |
| `POST,DELETE` | `https://discord.com/api/v9/users/@me/devices` | List or register push-notification devices for the current user |
| `PUT` | `https://discord.com/api/v9/users/@me/devices/sync` | Synchronize the current user's registered devices |
| `GET` | `https://discord.com/api/v9/users/@me/devices/sync-token` | Obtain a sync token for cross-device synchronization |
| `POST` | `https://discord.com/api/v9/users/@me/disable` | Disable (deactivate) the current user's account |
| `GET` | `https://discord.com/api/v9/users/@me/dms/{id}` | Fetch or manage a specific direct message channel of the current user |
| `PUT` | `https://discord.com/api/v9/users/@me/email` | Get or update the current user's email address |
| `GET` | `https://discord.com/api/v9/users/@me/email-settings` | Get or update the current user's email notification settings |
| `POST` | `https://discord.com/api/v9/users/@me/email/verify-code` | Submit/verify the email verification code for the current user |
| `GET` | `https://discord.com/api/v9/users/@me/embedded-survey/action` | Record an action taken on an embedded in-client survey |
| `GET` | `https://discord.com/api/v9/users/@me/embedded-survey/{id}` | Fetch a specific embedded in-client survey for the current user |
| `POST` | `https://discord.com/api/v9/users/@me/embedded-surveys/{id}/responses` | Submit responses to a specific embedded survey |
| `GET` | `https://discord.com/api/v9/users/@me/entitlements` | List the current user's entitlements (purchased/granted products) |
| `GET` | `https://discord.com/api/v9/users/@me/entitlements/gift-codes` | List gift codes owned by the current user |
| `DELETE` | `https://discord.com/api/v9/users/@me/entitlements/gift-codes/{id}` | Fetch or redeem/revoke a specific gift code owned by the user |
| `GET` | `https://discord.com/api/v9/users/@me/entitlements/gifts` | List gifts available to or sent by the current user |
| `PUT,DELETE` | `https://discord.com/api/v9/users/@me/game-relationships/{id}/{id}` | Manage a specific game-based relationship between the user and another user |
| `GET` | `https://discord.com/api/v9/users/@me/gravity-attachments` | List/manage Gravity (activity feed) attachments for the current user |
| `POST` | `https://discord.com/api/v9/users/@me/gravity-attachments-upload` | Request an upload slot for a Gravity (activity feed) attachment |
| `GET` | `https://discord.com/api/v9/users/@me/gravity-icymi` | Fetch the current user's Gravity "in case you missed it" feed items |
| `GET` | `https://discord.com/api/v9/users/@me/guilds/integration-application-ids` | List application IDs integrated across the current user's guilds |
| `GET` | `https://discord.com/api/v9/users/@me/guilds/premium/subscription-slots` | List the current user's Nitro guild-boost subscription slots |
| `POST` | `https://discord.com/api/v9/users/@me/guilds/premium/subscription-slots/{id}/cancel` | Cancel a specific guild-boost subscription slot |
| `POST` | `https://discord.com/api/v9/users/@me/guilds/premium/subscription-slots/{id}/uncancel` | Reverse cancellation of a specific guild-boost subscription slot |
| `GET` | `https://discord.com/api/v9/users/@me/guilds/premium/subscriptions` | List or create the current user's guild-boost (premium) subscriptions |
| `GET` | `https://discord.com/api/v9/users/@me/guilds/premium/subscriptions/cooldown` | Get the cooldown state for changing guild-boost subscriptions |
| `PATCH,DELETE` | `https://discord.com/api/v9/users/@me/guilds/settings` | Get or update the current user's per-guild settings across all guilds |
| `POST` | `https://discord.com/api/v9/users/@me/guilds/{id}/member/ack-dm-upsell-settings` | Acknowledge DM-upsell settings for the user's member in a specific guild |
| `PATCH` | `https://discord.com/api/v9/users/@me/guilds/{id}/settings` | Get or update the current user's notification/settings for a specific guild |
| `GET` | `https://discord.com/api/v9/users/@me/harvest` | Request or check status of the current user's data harvest (data download) |
| `GET` | `https://discord.com/api/v9/users/@me/invites` | List or accept invites associated with the current user |
| `GET` | `https://discord.com/api/v9/users/@me/join-request-guilds` | List guilds the current user has pending join requests for |
| `GET` | `https://discord.com/api/v9/users/@me/library` | List applications/games in the current user's library |
| `PATCH,DELETE` | `https://discord.com/api/v9/users/@me/library/{id}/{id}` | Fetch or manage a specific branch/SKU of a library application entry |
| `POST` | `https://discord.com/api/v9/users/@me/library/{id}/{id}/installed` | Get or set the installed state of a specific library application branch |
| `GET` | `https://discord.com/api/v9/users/@me/linked-users` | List accounts linked to the current user (e.g. family/linked accounts) |
| `POST` | `https://discord.com/api/v9/users/@me/meaningfully-online` | Report/get the user's "meaningfully online" presence status |
| `GET` | `https://discord.com/api/v9/users/@me/mentions` | List recent messages where the current user was mentioned |
| `DELETE` | `https://discord.com/api/v9/users/@me/mentions/{id}` | Dismiss/acknowledge a specific mention of the current user |
| `GET` | `https://discord.com/api/v9/users/@me/message-requests/supplemental-data` | Fetch supplemental data for the current user's message (DM) requests |
| `POST` | `https://discord.com/api/v9/users/@me/messages/search/tabs` | Get the configured search tabs for the user's message search |
| `POST` | `https://discord.com/api/v9/users/@me/mfa/codes-verification` | Verify MFA backup codes for the current user |
| `POST` | `https://discord.com/api/v9/users/@me/mfa/sms/disable` | Disable SMS-based two-factor authentication for the current user |
| `POST` | `https://discord.com/api/v9/users/@me/mfa/sms/enable` | Enable SMS-based two-factor authentication for the current user |
| `POST` | `https://discord.com/api/v9/users/@me/mfa/totp/disable` | Disable TOTP (authenticator) two-factor authentication for the current user |
| `POST` | `https://discord.com/api/v9/users/@me/mfa/totp/enable` | Enable TOTP (authenticator) two-factor authentication for the current user |
| `GET` | `https://discord.com/api/v9/users/@me/mfa/webauthn/credentials` | List or register WebAuthn (security key) MFA credentials for the user |
| `PATCH,DELETE` | `https://discord.com/api/v9/users/@me/mfa/webauthn/credentials/{id}` | Fetch, rename, or delete a specific WebAuthn MFA credential |
| `GET` | `https://discord.com/api/v9/users/@me/notes` | List the current user's private notes on other users |
| `GET` | `https://discord.com/api/v9/users/@me/notes/{id}` | Get or set the current user's private note on a specific user |
| `? (id-gated)` | `https://discord.com/api/v9/users/@me/notification-center/items${null!=e?` | List notification-center items for the current user (with optional query params) |
| `POST,DELETE` | `https://discord.com/api/v9/users/@me/notification-center/items/bulk-ack` | Bulk-acknowledge multiple notification-center items |
| `POST` | `https://discord.com/api/v9/users/@me/notification-center/items/{id}/ack` | Acknowledge a specific notification-center item |
| `PATCH` | `https://discord.com/api/v9/users/@me/notification-settings` | Get or update the current user's global notification settings |
| `GET` | `https://discord.com/api/v9/users/@me/notification-settings/muted-games` | List games muted in the current user's notification settings |
| `PATCH` | `https://discord.com/api/v9/users/@me/notification-settings/muted-games/{id}` | Mute/unmute notifications for a specific game in the user's settings |
| `GET` | `https://discord.com/api/v9/users/@me/notification-settings/snapshots` | Lists or creates saved snapshots of the current user's notification settings |
| `DELETE` | `https://discord.com/api/v9/users/@me/notification-settings/snapshots/{id}` | Fetches, updates, or deletes a specific notification-settings snapshot by snapshot ID |
| `POST` | `https://discord.com/api/v9/users/@me/notification-settings/snapshots/{id}/restore-guilds` | Restores per-guild notification settings from the given snapshot for the current user |
| `GET` | `https://discord.com/api/v9/users/@me/outbound-promotions/codes` | Lists outbound promotion/partner promo codes granted to the current user |
| `POST,DELETE` | `https://discord.com/api/v9/users/@me/partner-perks/{id}` | Fetches details of a specific partner-perk entitlement by perk ID for the current user |
| `GET` | `https://discord.com/api/v9/users/@me/partner-perks/{id}/activation-status` | Gets or updates the activation status of the current user's partner perk by perk ID |
| `POST,DELETE` | `https://discord.com/api/v9/users/@me/phone` | Sets, changes, or removes the current user's phone number |
| `POST` | `https://discord.com/api/v9/users/@me/phone/reverify` | Triggers re-verification of the current user's existing phone number |
| `POST` | `https://discord.com/api/v9/users/@me/phone/verify` | Submits the SMS verification code to verify the current user's phone number |
| `POST` | `https://discord.com/api/v9/users/@me/pomelo` | Completes the current user's migration to the new unique-username (Pomelo) system |
| `POST` | `https://discord.com/api/v9/users/@me/pomelo-attempt` | Submits/validates a candidate unique username during Pomelo migration for the current user |
| `GET` | `https://discord.com/api/v9/users/@me/pomelo-suggestions` | Returns suggested available unique usernames for the current user's Pomelo migration |
| `GET` | `https://discord.com/api/v9/users/@me/premium-group/invites` | Lists or creates invites for the current user's Nitro/premium family-group sharing |
| `GET` | `https://discord.com/api/v9/users/@me/premium-group/invites/{id}` | Fetches, accepts, or revokes a specific premium-group invite by invite ID |
| `GET` | `https://discord.com/api/v9/users/@me/premium-group/membership` | Gets or manages the current user's membership in a shared premium group |
| `GET` | `https://discord.com/api/v9/users/@me/premium-usage` | Returns the current user's premium (Nitro) feature usage statistics |
| `GET` | `https://discord.com/api/v9/users/@me/program-rewards` | Lists rewards available to the current user from Discord programs (e.g. partner/dev programs) |
| `GET` | `https://discord.com/api/v9/users/@me/referrals/eligibility` | Checks whether the current user is eligible to send referrals |
| `POST` | `https://discord.com/api/v9/users/@me/referrals/eligible-users` | Lists users the current user is eligible to refer |
| `POST` | `https://discord.com/api/v9/users/@me/referrals/{id}` | Fetches or acts on a specific referral by referral ID for the current user |
| `POST,PUT,PATCH,DELETE` | `https://discord.com/api/v9/users/@me/relationships/bulk` | Performs bulk operations (add/remove) on the current user's friend/relationship list |
| `PUT,PATCH,DELETE` | `https://discord.com/api/v9/users/@me/relationships/{id}` | Adds, accepts, or removes the relationship (friend/block) with the given user ID |
| `PUT,DELETE` | `https://discord.com/api/v9/users/@me/relationships/{id}/ignore` | Sets or clears the "ignore" state on the relationship with the given user ID |
| `POST` | `https://discord.com/api/v9/users/@me/remote-auth` | Initiates a remote-authentication (QR-code login) session for the current user |
| `POST` | `https://discord.com/api/v9/users/@me/remote-auth/cancel` | Cancels a pending remote-authentication (QR-code login) session |
| `POST` | `https://discord.com/api/v9/users/@me/remote-auth/finish` | Finalizes a remote-authentication session, authorizing login on the remote device |
| `POST` | `https://discord.com/api/v9/users/@me/remote-auth/login` | Approves the remote-authentication login request, issuing credentials to the remote device |
| `GET` | `https://discord.com/api/v9/users/@me/saved-messages` | Lists or creates the current user's saved/bookmarked messages |
| `PUT,DELETE` | `https://discord.com/api/v9/users/@me/saved-messages/{id}/{id}` | Fetches or deletes a specific saved message identified by channel ID and message ID |
| `GET` | `https://discord.com/api/v9/users/@me/scheduled-events` | Lists guild scheduled events relevant to (RSVP'd by) the current user |
| `GET` | `https://discord.com/api/v9/users/@me/scheduled-messages` | Lists or creates the current user's scheduled (send-later) messages |
| `PATCH,DELETE` | `https://discord.com/api/v9/users/@me/scheduled-messages/{id}` | Fetches, edits, or cancels a specific scheduled message by its ID |
| `GET` | `https://discord.com/api/v9/users/@me/settings` | Gets or updates the current user's client/account settings |
| `GET` | `https://discord.com/api/v9/users/@me/settings-proto/{id}` | Gets or updates a protobuf-encoded settings document (by settings type ID) for the current user |
| `POST` | `https://discord.com/api/v9/users/@me/summaries` | Lists AI-generated conversation summaries available to the current user |
| `GET` | `https://discord.com/api/v9/users/@me/survey` | Fetches the current in-product survey offered to the user |
| `POST` | `https://discord.com/api/v9/users/@me/survey/{id}/seen` | Marks the given survey ID as seen/dismissed by the current user |
| `GET` | `https://discord.com/api/v9/users/@me/unclaimed-games` | Lists free/promotional games the current user has not yet claimed |
| `GET` | `https://discord.com/api/v9/users/@me/valid-collectibles-gift-recipient` | Checks whether a given user is a valid recipient for a collectibles gift |
| `GET` | `https://discord.com/api/v9/users/@me/valid-collectibles-gift-recipients-batch` | Batch-checks multiple users for collectibles-gift recipient eligibility |
| `GET` | `https://discord.com/api/v9/users/@me/video-filters/assets` | Lists or uploads the current user's video-filter (camera effect) assets |
| `DELETE` | `https://discord.com/api/v9/users/@me/video-filters/assets/{id}` | Fetches, updates, or deletes a specific video-filter asset by asset ID |
| `POST` | `https://discord.com/api/v9/users/@me/video-filters/assets/{id}/last-used` | Updates the last-used timestamp for the given video-filter asset |
| `GET` | `https://discord.com/api/v9/users/@me/virtual-currency/balance` | Returns the current user's virtual-currency (Orbs) balance |
| `PUT` | `https://discord.com/api/v9/users/@me/widgets` | Lists or manages the current user's home/dashboard widgets |
| `GET` | `https://discord.com/api/v9/users/@me/widgets/application-widget-application-ids` | Returns the application IDs eligible for application widgets for the current user |
| `GET` | `https://discord.com/api/v9/users/@me/widgets/suggested-games` | Returns suggested games to surface in the current user's widgets |
| `POST` | `https://discord.com/api/v9/users/@me/wishlist/items` | Lists or adds items to the current user's store wishlist |
| `PATCH` | `https://discord.com/api/v9/users/@me/wishlists/{id}` | Fetches, updates, or deletes a specific wishlist by wishlist ID |
| `PATCH,DELETE` | `https://discord.com/api/v9/users/@me/wishlists/{id}/items/{id}` | Fetches or removes a specific item within a specific wishlist |
| `POST` | `https://discord.com/api/v9/users/@me/{id}/{id}/ack` | Acknowledges (marks read) a message identified by channel ID and message ID for the current user |
| `GET` | `https://discord.com/api/v9/users/disable-email-notifications` | Unsubscribes/disables email notifications (typically via a tokenized email link) |
| `GET` | `https://discord.com/api/v9/users/disable-server-highlight-notifications` | Disables server-highlights email notifications for the user (via tokenized link) |
| `GET` | `https://discord.com/api/v9/users/{id}/application-identities` | Lists the application/linked identities associated with the given user ID |
| `GET` | `https://discord.com/api/v9/users/{id}/profile` | Gets the full profile (bio, badges, connections, mutuals) for the given user ID |
| `GET` | `https://discord.com/api/v9/users/{id}/relationships` | Returns the mutual-friend relationships between the current user and the given user ID |
| `GET` | `https://discord.com/api/v9/users/{id}/sessions/{id}/activities/{id}/1` | Accesses a specific rich-presence activity instance (party/slot 1) within a user's session |
| `GET` | `https://discord.com/api/v9/users/{id}/sessions/{id}/activities/{id}/metadata` | Fetches metadata for a specific activity in the given user's session |
| `PUT` | `https://discord.com/api/v9/voice/public-keys` | Returns the voice server public keys used for end-to-end encrypted voice (DAVE) |
| `POST` | `https://discord.com/api/v9/voice/{id}/match-public-key` | Matches/validates a participant's voice public key for the given voice session ID |
| `? (id-gated)` | `https://discord.com/api/v9/voice/{id}/{id}` | Accesses a specific voice resource keyed by voice session ID and a sub-resource ID |
| `GET` | `https://discord.com/api/v9/apex/experiments` | Get APEX experiment assignments/configuration for the client |
| `GET` | `https://discord.com/api/v9/apex/experiments/metadata` | Get metadata describing available APEX experiments |
| `GET` | `https://discord.com/api/v9/applications-with-assets` | List the user's applications including their associated assets |
| `GET` | `https://discord.com/api/v9/beaker` | Internal experiment/feature-flag (Beaker) endpoint |
| `GET` | `https://discord.com/api/v9/bogo-promotions` | List buy-one-get-one promotional offers |
| `POST` | `https://discord.com/api/v9/branches` | List application/build branches (developer build distribution) |
| `POST` | `https://discord.com/api/v9/captcha/decider` | Decide whether a captcha challenge is required for a request |
| `GET` | `https://discord.com/api/v9/collectibles-categories` | List collectibles (avatar decorations/profile effects) categories |
| `GET` | `https://discord.com/api/v9/collectibles-categories/v2` | List collectibles categories (v2 schema) |
| `GET` | `https://discord.com/api/v9/collectibles-products/{id}` | Get a specific collectibles product |
| `GET` | `https://discord.com/api/v9/collectibles-shop` | Get the collectibles shop storefront |
| `GET` | `https://discord.com/api/v9/collectibles-shop-tab-layouts/{id}` | Get the layout configuration for a collectibles shop tab |
| `POST` | `https://discord.com/api/v9/debug-logs/multi/{id}` | Submit or retrieve a multi-part debug log bundle |
| `POST` | `https://discord.com/api/v9/debug-logs/{id}/{id}` | Access a specific debug log entry by nested IDs |
| `GET` | `https://discord.com/api/v9/discoverable-guilds` | List guilds available in server discovery |
| `GET` | `https://discord.com/api/v9/discoverable-guilds/mobile-game-communities` | List discoverable guilds in the mobile-game-communities category |
| `GET` | `https://discord.com/api/v9/discoverable-guilds/search` | Search discoverable guilds in server discovery |
| `GET` | `https://discord.com/api/v9/emojis/{id}/guild` | Get the guild that owns a given emoji by emoji ID |
| `GET` | `https://discord.com/api/v9/emojis/{id}/source` | Get the source (origin guild/application) of an emoji by emoji ID |
| `? (id-gated)` | `https://discord.com/api/v9/entitlements/gift-codes/{id}` | Resolve a gift code's entitlement details by gift code |
| `POST` | `https://discord.com/api/v9/entitlements/gift-codes/{id}/redeem` | Redeem a gift code to grant the entitlement to the current user |
| `POST` | `https://discord.com/api/v9/entitlements/partner-promotions/{id}` | Get/claim a partner-promotion entitlement by promotion ID |
| `GET` | `https://discord.com/api/v9/experiments` | Fetch the current user's active experiment (A/B feature-flag) assignments |
| `POST` | `https://discord.com/api/v9/friend-finder/find-friends` | Find friends by matching uploaded contacts (contact sync) |
| `GET` | `https://discord.com/api/v9/friend-suggestions` | List friend suggestions for the current user |
| `DELETE` | `https://discord.com/api/v9/friend-suggestions/{id}` | Get/dismiss a specific friend suggestion by suggested-user ID |
| `? (id-gated)` | `https://discord.com/api/v9/game-invite/@me/{id}` | Get/accept/decline a specific game invite for the current user by invite ID |
| `GET` | `https://discord.com/api/v9/generated-pools/@me` | Get the current user's generated content/recommendation pools |
| `GET` | `https://discord.com/api/v9/generated-pools/{id}` | Get a generated content/recommendation pool by ID |
| `POST` | `https://discord.com/api/v9/google-play/downgrade-subscription` | Downgrade a Discord subscription purchased via Google Play billing |
| `POST` | `https://discord.com/api/v9/google-play/validate-purchase` | Validate a Google Play purchase for an entitlement/subscription |
| `POST` | `https://discord.com/api/v9/google-play/verify-purchase-token` | Verify a Google Play purchase token to grant an entitlement |
| `POST` | `https://discord.com/api/v9/gravity-content` | Fetch personalized "Gravity" home-feed recommendation content for the current user |
| `GET` | `https://discord.com/api/v9/gravity-custom-channel-scores` | Submit/fetch custom relevance scores for channels used by the Gravity recommendation engine |
| `PUT` | `https://discord.com/api/v9/gravity-custom-guild-score` | Submit/fetch a custom relevance score for a guild used by the Gravity recommendation engine |
| `GET` | `https://discord.com/api/v9/gravity-recommended-guilds` | List guilds recommended to the current user by the Gravity engine |
| `POST` | `https://discord.com/api/v9/gravity-topic-guilds` | List guilds recommended by topic for the Gravity engine |
| `? (id-gated)` | `https://discord.com/api/v9/guild-stages/{id}${null!=t?` | Fetch a specific guild stage instance (template-built URL with optional query suffix) |
| `POST` | `https://discord.com/api/v9/holidays/redeem-prize` | Redeem a prize from a seasonal/holiday promotional event |
| `POST` | `https://discord.com/api/v9/hub-waitlist/signup` | Sign up to the Student Hub waitlist |
| `POST` | `https://discord.com/api/v9/initiate-prompts` | Start onboarding/contextual prompt flows for the user |
| `POST` | `https://discord.com/api/v9/integrations/{id}/join` | Join a guild/resource via a specific integration |
| `GET` | `https://discord.com/api/v9/integrations/{id}/search` | Search within a specific integration's content |
| `POST` | `https://discord.com/api/v9/interactions` | Submit/dispatch an application interaction (slash command, component, modal) |
| `GET` | `https://discord.com/api/v9/invites/{id}/friend-members` | List the current user's friends who are members of the invited guild/channel |
| `GET` | `https://discord.com/api/v9/join-requests/{id}` | Fetch or act on a specific guild join request by its ID |
| `POST` | `https://discord.com/api/v9/join-requests/{id}/interview` | Get or submit the membership-screening interview questions/answers for a join request |
| `GET` | `https://discord.com/api/v9/layouts/{id}/{id}` | Fetch a nested layout resource (layout container ID then item ID) |
| `? (id-gated)` | `https://discord.com/api/v9/member-verification-for-hub/{id}${null!=t?` | Fetch student-hub member-verification (gate/rules) data for a hub by ID (templated client URL) |
| `POST` | `https://discord.com/api/v9/messages-log/guild-channels/get` | Retrieve message audit/log entries for guild channels (moderation/T&S tooling) |
| `POST` | `https://discord.com/api/v9/messages-log/private-channels/get` | Retrieve message audit/log entries for private channels/DMs (moderation/T&S tooling) |
| `PATCH` | `https://discord.com/api/v9/messages/explicit-media` | Report/scan or fetch explicit-media classification state for messages |
| `POST` | `https://discord.com/api/v9/metrics` | Client/analytics telemetry ingestion endpoint for event metrics |
| `POST` | `https://discord.com/api/v9/metrics/v2` | Version 2 client/analytics telemetry ingestion endpoint for event metrics |
| `POST` | `https://discord.com/api/v9/mfa/finish` | Complete a multi-factor authentication challenge and finalize the MFA-elevated session |
| `POST` | `https://discord.com/api/v9/mod-report/{id}/close` | Close a moderation report by its report ID |
| `PUT` | `https://discord.com/api/v9/mod-report/{id}/reopen` | Reopen a previously closed moderation report by its report ID |
| `POST` | `https://discord.com/api/v9/networking/token` | Issue a networking/voice-relay (e.g. WebRTC/ICE) auth token for the client |
| `? (id-gated)` | `https://discord.com/api/v9/outbound-promotions/{id}/claim` | Claim an outbound partner promotion/offer by its promotion ID |
| `POST` | `https://discord.com/api/v9/phone-verifications/resend` | Resend the SMS phone-verification code to the user |
| `POST` | `https://discord.com/api/v9/phone-verifications/validate-support-ticket` | Validate a phone number against a support ticket during account recovery/verification |
| `POST` | `https://discord.com/api/v9/phone-verifications/verify` | Submit and verify the SMS phone-verification code |
| `POST` | `https://discord.com/api/v9/platform-application` | Get platform/console application linking info (e.g. PlayStation/Xbox integration) |
| `? (id-gated)` | `https://discord.com/api/v9/playlist/{id}` | Fetch a media/activity playlist (e.g. Watch Together queue) by its ID |
| `GET` | `https://discord.com/api/v9/premium-marketing/@me/campaigns/{id}/eligibility` | Check the current user's eligibility for a premium (Nitro) marketing campaign by campaign ID |
| `GET` | `https://discord.com/api/v9/private/bug-reports` | Internal/private bug-report submission endpoint |
| `GET` | `https://discord.com/api/v9/promotions` | List available promotions/offers (e.g. Nitro deals) for the current user |
| `POST` | `https://discord.com/api/v9/read-states/ack-bulk` | Bulk-acknowledge (mark as read) multiple channel read states |
| `GET` | `https://discord.com/api/v9/referrals/{id}` | Fetch or act on a referral by its ID |
| `GET` | `https://discord.com/api/v9/report` | Submit a user/content abuse report |
| `GET` | `https://discord.com/api/v9/report/options` | Fetch the available report reasons/options menu |
| `POST` | `https://discord.com/api/v9/reports` | List or submit reports |
| `POST` | `https://discord.com/api/v9/reports/channels/{id}/messages/{id}` | Report a specific message in a specific channel |
| `GET` | `https://discord.com/api/v9/roblox-applications-supplemental-data` | Fetch supplemental data for linked Roblox applications |
| `POST` | `https://discord.com/api/v9/safety-flows/resend/email/reverification/pincode` | Resend the email reverification PIN code in a safety flow |
| `GET` | `https://discord.com/api/v9/safety-flows/task` | Fetch or submit a safety-flow remediation task |
| `GET` | `https://discord.com/api/v9/science` | Submit client analytics/telemetry events (Science) |
| `GET` | `https://discord.com/api/v9/soundboard-sounds/{id}/guild/{id}` | Fetch a soundboard sound by ID scoped to a specific guild |
| `GET` | `https://discord.com/api/v9/sso` | Single sign-on authentication entry point |
| `GET` | `https://discord.com/api/v9/sso-token` | Fetch/exchange an SSO token |
| `GET` | `https://discord.com/api/v9/stage-instances/extra` | Fetch supplementary Stage instance data |
| `GET` | `https://discord.com/api/v9/sticker-packs/directory-v2/{id}` | Fetch a sticker-pack directory (v2) entry by its ID |
| `GET` | `https://discord.com/api/v9/stickers/{id}.{id}` | Fetch a sticker asset by sticker ID and asset/format hash |
| `GET` | `https://discord.com/api/v9/stickers/{id}/guild` | Fetch the guild that owns a given sticker by sticker ID |
| `GET` | `https://discord.com/api/v9/subscription-plans/{id}/guild-role-subscription-group-listing` | Get the guild role-subscription group listing for a given subscription plan |
| `GET` | `https://discord.com/api/v9/subscription-plans/{id}/subscription-group-listing` | Get the subscription group listing for a given subscription plan |
| `GET` | `https://discord.com/api/v9/teams` | Manage developer teams (create/list teams that own applications) |
| `GET` | `https://discord.com/api/v9/templates/{id}/{id}` | Get a nested template resource by template ID and sub-resource ID |
| `POST,PUT` | `https://discord.com/api/v9/tutorial/indicators/suppress` | Suppress (dismiss) the current user's tutorial indicators |
| `PUT` | `https://discord.com/api/v9/tutorial/indicators/{id}` | Mark/dismiss a specific tutorial indicator by ID for the current user |
| `POST` | `https://discord.com/api/v9/unfurler/embed-urls` | Unfurl URLs into rich embeds (server-side link metadata/preview generation) |
| `POST` | `https://discord.com/api/v9/unique-username/username-attempt-unauthed` | Check availability of a desired unique username without authentication (pomelo onboarding) |
| `GET` | `https://discord.com/api/v9/unique-username/username-suggestions-unauthed` | Get suggested available unique usernames without authentication (pomelo onboarding) |
| `POST` | `https://discord.com/api/v9/unverified-applications` | Manage unverified applications (apps not yet through Discord verification) |
| `POST` | `https://discord.com/api/v9/unverified-applications/icons` | Upload/manage icons for unverified applications |
| `POST` | `https://discord.com/api/v9/virtual-currency/skus/{id}/redeem` | Redeems virtual currency against the SKU identified by SKU ID |
| `? (id-gated)` | `https://discord.com/api/v9/voice-hangouts/{id}/{id}` | Accesses a specific voice-hangout resource keyed by two IDs (e.g. hangout ID + member/session ID) |
| `? (id-gated)` | `https://discord.com/api/v9/v{id}` | API/resource version-prefixed path or versioned short token |
| `GET` | `https://discord.com/api/v9/widget-configs/developer` | Returns developer-defined widget configuration definitions |
| `GET` | `https://discord.com/api/v9/widget-configs/featured` | Returns the featured/curated widget configurations |
| `GET` | `https://discord.com/api/v9/wishlist/gift-recommendations` | Returns gift recommendations derived from wishlist data |
| `GET` | `https://discord.com/api/v9/wishlists/{id}` | Fetches, updates, or deletes a specific wishlist by wishlist ID |

## Web / app routes — discord.com/… (NOT the API)

| Method(s) | Endpoint (URL / path) | Meaning |
|---|---|---|
| `GET` | `https://discord.com/activities/applications/{id}/activity-instances/{id}/join` | Join a running activity instance for the given application |
| `GET` | `https://discord.com/activities/happening-now` | List activities currently happening now across the user's surfaces (live/popular sessions) |
| `GET` | `https://discord.com/activities/{id}` | Get details for a specific activity by ID |
| `GET` | `https://discord.com/app` | Root web-app/application bootstrap resource |
| `GET` | `https://discord.com/app/gifts/{id}` | Resolve/view an in-app gift by ID |
| `GET` | `https://discord.com/app/invite-with-guild-onboarding/{id}` | Resolve an invite that triggers guild onboarding for the given invite/guild |
| `GET` | `https://discord.com/application-directory` | Access the Application Directory (app discovery storefront) root |
| `GET` | `https://discord.com/application-directory/collection-items/{id}/{id}.{id}` | Get a specific App Directory collection item asset by collection/item IDs |
| `GET` | `https://discord.com/application-directory/{id}` | Get an App Directory entry by ID |
| `GET` | `https://discord.com/application-directory/{id}/{id}` | Get a nested App Directory sub-resource under the given entry |
| `GET` | `https://discord.com/application-directory/{id}/{id}/{id}` | Get a deeply-nested App Directory sub-resource under the given entry |
| `GET` | `https://discord.com/archive/` | Access the archive root (historical legal/policy documents) |
| `GET` | `https://discord.com/archive/guidelines/may-2020` | Retrieve the archived May 2020 community guidelines document |
| `GET` | `https://discord.com/attachments/` | Serve/access uploaded message attachment files (CDN-style root) |
| `GET` | `https://discord.com/billing/apple/subscriptions/{id}` | Get/manage a specific Apple-billed subscription by ID |
| `GET` | `https://discord.com/billing/guild-subscriptions/purchase` | Purchase a guild subscription (server boosts) |
| `GET` | `https://discord.com/billing/login/handoff` | Hand off an authenticated session into the billing flow |
| `GET` | `https://discord.com/billing/partner-promotions/{id}/{id}` | Get a specific partner-promotion offer/claim by IDs |
| `GET` | `https://discord.com/billing/payment-sources/create` | Add a new payment source (card/PayPal) to the account |
| `GET` | `https://discord.com/billing/payments` | List the current user's payment history |
| `GET` | `https://discord.com/billing/premium/manage` | Manage the current user's Nitro (premium) subscription |
| `GET` | `https://discord.com/billing/premium/subscribe` | Subscribe to Nitro (premium) |
| `GET` | `https://discord.com/billing/premium/switch-plan` | Switch the current Nitro plan/tier |
| `GET` | `https://discord.com/billing/promotions` | List available billing promotions for the user |
| `GET` | `https://discord.com/billing/promotions/{id}` | Get/claim a specific billing promotion by ID |
| `GET` | `https://discord.com/billing/store-country` | Get the user's store/billing country |
| `GET` | `https://discord.com/channels/` | Channels collection endpoint (trailing-slash variant) |
| `GET` | `https://discord.com/channels/{id}/boosts` | Get boost info for a channel |
| `GET` | `https://discord.com/channels/{id}/convert` | Convert a channel to a different type |
| `GET` | `https://discord.com/channels/{id}/game-shop` | Get game-shop content associated with a channel |
| `GET` | `https://discord.com/channels/{id}/icons/{id}.jpg` | Fetch a group-DM channel icon image |
| `GET` | `https://discord.com/channels/{id}/recipients` | Manage recipients of a group DM channel |
| `GET` | `https://discord.com/channels/{id}/shop` | Get the shop/storefront listings for a channel |
| `GET` | `https://discord.com/channels/{id}/shop/{id}` | Get a specific shop item/listing in a channel |
| `GET` | `https://discord.com/channels/{id}/threads/archived/{id}` | Access archived threads of a channel paginated by ID |
| `GET` | `https://discord.com/channels/{id}/voice-history` | Fetch the voice activity history of a channel |
| `GET` | `https://discord.com/channels/{id}/{id}` | Access a sub-resource of a channel identified by a snowflake ID |
| `GET` | `https://discord.com/channels/{id}/{id}/threads/{id}` | Access a specific thread under a channel sub-resource |
| `GET` | `https://discord.com/channels/{id}/{id}/{id}` | Access a nested sub-resource of a channel by snowflake ID |
| `GET` | `https://discord.com/conference-mode` | Conference mode root resource |
| `GET` | `https://discord.com/connections/xbox/intro` | Get the Xbox connection introduction/onboarding info |
| `GET` | `https://discord.com/connections/xbox/pin` | Get or submit the Xbox account linking PIN |
| `GET` | `https://discord.com/connections/{id}` | Get, update, or delete a specific external account connection |
| `GET` | `https://discord.com/connections/{id}/authorize-continue` | Continue a connection provider authorization flow |
| `GET` | `https://discord.com/connections/{id}/error` | Report or retrieve an error from a connection flow |
| `GET` | `https://discord.com/connections/{id}/success` | Mark or retrieve success state for a connection flow |
| `GET` | `https://discord.com/dev/` | Unix device directory reference (not a Discord API route; static string from bundled code) |
| `GET` | `https://discord.com/developers` | Discord Developer Portal landing page |
| `GET` | `https://discord.com/developers/applications` | List/manage the current user's developer applications in the Developer Portal |
| `GET` | `https://discord.com/developers/applications/select/game-identity` | Application selector flow for configuring a game's identity in the Developer Portal |
| `GET` | `https://discord.com/developers/docs` | Discord developer documentation portal |
| `GET` | `https://discord.com/developers/servers/{id}` | Developer Portal management page for a specific server (guild) by ID |
| `GET` | `https://discord.com/developers/teams` | List/manage developer teams in the Developer Portal |
| `GET` | `https://discord.com/developers/teams/{id}/payout-settings` | Configure payout (monetization payment) settings for a developer team by ID |
| `GET` | `https://discord.com/discovery` | Server/application discovery home surface |
| `GET` | `https://discord.com/discovery/applications` | List discoverable applications (activities/games) in discovery |
| `GET` | `https://discord.com/discovery/applications/categories/{id}` | List applications in a specific discovery category by ID |
| `GET` | `https://discord.com/discovery/applications/search` | Search discoverable applications in discovery |
| `GET` | `https://discord.com/discovery/applications/{id}` | Get a discoverable application's discovery listing by application ID |
| `GET` | `https://discord.com/discovery/applications/{id}/{id}` | Get a sub-resource of a discoverable application's discovery listing (e.g. category/section) by IDs |
| `GET` | `https://discord.com/discovery/applications/{id}/{id}/{id}` | Get a nested sub-resource within a discoverable application's discovery listing by IDs |
| `GET` | `https://discord.com/discovery/quests` | List quests surfaced in discovery |
| `GET` | `https://discord.com/discovery/servers` | List discoverable servers (guilds) in discovery |
| `GET` | `https://discord.com/family-center` | Family Center landing/overview surface |
| `GET` | `https://discord.com/games/` | List games (game store/library catalog, trailing-slash variant) |
| `GET` | `https://discord.com/games/{id}/updates/{id}` | Get a specific update/patch record for a game by game ID and update ID |
| `GET` | `https://discord.com/guilds/{id}/analytics/overview` | Get the overall analytics overview for a guild |
| `GET` | `https://discord.com/guilds/{id}/avatars/{id}.{id}` | Fetch a specific guild-scoped member avatar image asset (by hash/extension) |
| `GET` | `https://discord.com/guilds/{id}/banners/{id}.{id}` | Fetch a specific guild banner image asset (by hash/extension) |
| `GET` | `https://discord.com/guilds/{id}/creator-monetization/accept-new-terms` | Accept updated creator-monetization terms for a guild |
| `GET` | `https://discord.com/guilds/{id}/discovery-checklist` | Get the discovery-eligibility checklist for a guild |
| `GET` | `https://discord.com/guilds/{id}/discovery-splashes/{id}.jpg` | Fetch a specific discovery splash image asset for a guild |
| `GET` | `https://discord.com/guilds/{id}/home-headers/{id}.jpg` | Fetch a specific guild home header image asset |
| `GET` | `https://discord.com/guilds/{id}/icons/{id}.{id}` | Fetch a specific guild icon image asset (by hash/extension) |
| `GET` | `https://discord.com/guilds/{id}/members/{id}/nick` | Set the nickname of a specific member in a guild |
| `GET` | `https://discord.com/guilds/{id}/notification-settings` | Get or update the current user's notification settings for a guild |
| `GET` | `https://discord.com/guilds/{id}/powerups-system-message` | Get/configure the system message posted when a Power-up is applied to the guild |
| `GET` | `https://discord.com/guilds/{id}/premium-guild-subscriptions` | List the guild's premium (Nitro Boost) subscription slots |
| `GET` | `https://discord.com/guilds/{id}/profile/{id}` | Get/update a specific sub-section/entry of the guild profile by ID |
| `GET` | `https://discord.com/guilds/{id}/splashes/{id}.jpg` | Fetch the guild's invite splash image asset (CDN-style JPG by hash) |
| `GET` | `https://discord.com/guilds/{id}/users/{id}/avatars/{id}.{id}` | Fetch a member's per-guild avatar image asset (CDN-style by hash/extension) |
| `GET` | `https://discord.com/guilds/{id}/users/{id}/banners/{id}.{id}` | Fetch a member's per-guild banner image asset (CDN-style by hash/extension) |
| `GET` | `https://discord.com/library` | List the current user's purchased/owned game and application library |
| `GET` | `https://discord.com/library/inventory` | Get the user's owned-application inventory entries from their library |
| `GET` | `https://discord.com/library/settings` | Get or update the user's game library display/visibility settings |
| `GET` | `https://discord.com/library/{id}/{id}` | Fetch a nested library item (application ID then SKU/branch ID) for the user |
| `GET` | `https://discord.com/new` | Discord blog/landing root (new-style marketing site index) |
| `GET` | `https://discord.com/new/acknowledgements` | Open-source/legal acknowledgements page on the marketing site |
| `GET` | `https://discord.com/new/branding` | Brand assets/guidelines page on the marketing site |
| `GET` | `https://discord.com/new/company` | Company/about page on the marketing site |
| `GET` | `https://discord.com/new/discord-xbox-offer-2019` | Landing page for the 2019 Discord Nitro x Xbox Game Pass promotional offer |
| `GET` | `https://discord.com/new/index` | Marketing site homepage/index |
| `GET` | `https://discord.com/new/licenses` | Third-party software licenses page on the marketing site |
| `GET` | `https://discord.com/new/nitro` | Nitro subscription marketing/landing page |
| `GET` | `https://discord.com/new/privacy` | Privacy policy page on the marketing site |
| `GET` | `https://discord.com/new/streamkit` | StreamKit (streamer overlay/tools) marketing page |
| `GET` | `https://discord.com/oauth2/authorized` | List the user's currently authorized OAuth2 applications |
| `GET` | `https://discord.com/oauth2/error` | OAuth2 authorization error display page |
| `GET` | `https://discord.com/partners` | Discord Partner Program landing/info page |
| `GET` | `https://discord.com/partners/apply` | Submit an application to the Discord Partner Program |
| `GET` | `https://discord.com/partners/connections` | Manage partner program connections/linked accounts |
| `GET` | `https://discord.com/partners/{id}/requirements` | Get the partner-program requirements/eligibility status for a guild by ID |
| `GET` | `https://discord.com/quests` | List all available Quests |
| `GET` | `https://discord.com/settings/` | User settings root surface |
| `GET` | `https://discord.com/settings/advanced/activate-application-test-mode` | Activate application test mode in advanced developer settings |
| `GET` | `https://discord.com/shop` | Fetch the Discord Shop (merch/Nitro storefront) landing |
| `GET` | `https://discord.com/shop/collection/{id}` | Fetch a Shop product collection by its ID |
| `GET` | `https://discord.com/shop/layout/{id}` | Fetch a Shop page layout by its ID |
| `GET` | `https://discord.com/shop/product/{id}` | Fetch a Shop product by its ID |
| `GET` | `https://discord.com/store` | Fetch the application store landing surface |
| `GET` | `https://discord.com/store/published-listings/skus/{id}/guild/join` | Join the guild associated with a published SKU listing (e.g. server linked to a purchasable product) |
| `GET` | `https://discord.com/terms` | Get Discord Terms of Service content |
| `GET` | `https://discord.com/users/` | User collection root (users base path) |
| `GET` | `https://discord.com/users/@me/activate-perk-demo/{id}` | Activate a demo of a premium perk by perk/SKU ID for the current user |
| `GET` | `https://discord.com/users/@me/billing/stripe/payment-intents/{id}` | Fetch/update a specific Stripe payment intent for the current user's billing flow |
| `GET` | `https://discord.com/users/@me/billing/subscriptions/{id}/promotion-reward` | Retrieve the promotion reward associated with the given subscription |
| `GET` | `https://discord.com/users/@me/billing/subscriptions/{id}/reactivation-offers/{id}/redeem` | Redeem a specific reactivation offer for a cancelled/expired subscription |
| `GET` | `https://discord.com/users/@me/billing/subscriptions/{id}/reward-eligibility` | Check the current user's eligibility for rewards on the given subscription |
| `GET` | `https://discord.com/users/@me/billing/subscriptions/{id}/rewards` | List rewards earned from the given subscription |
| `GET` | `https://discord.com/users/@me/burst-credits` | Get the current user's available burst (super) reaction credits |
| `GET` | `https://discord.com/users/@me/claim-reward-category-product` | Claim a product from a reward category for the current user |
| `GET` | `https://discord.com/users/@me/gravity-icymi-legacy` | Fetch the legacy version of the user's Gravity ICYMI feed |
| `GET` | `https://discord.com/users/@me/library/{id}` | Fetch or manage a specific library application entry |
| `GET` | `https://discord.com/users/@me/mfa/totp/enable/resend` | Resend the verification step while enabling TOTP two-factor authentication |
| `GET` | `https://discord.com/users/@me/mfa/totp/enable/verify` | Verify the TOTP code to complete enabling two-factor authentication |
| `GET` | `https://discord.com/users/@me/perks-demos` | Lists available perks demo/preview offers for the current user |
| `GET` | `https://discord.com/users/@me/settings/game-notifications` | Gets or updates the current user's game-activity notification settings |
| `GET` | `https://discord.com/users/@me/settings/game-notifications/overrides` | Gets or updates per-game overrides for the current user's game-notification settings |
| `GET` | `https://discord.com/users/@me/tenure-reward/sync` | Synchronizes/claims the current user's membership-tenure rewards |
| `GET` | `https://discord.com/users/{id}/avatars/{id}.{id}` | CDN-style fetch of a specific avatar image (avatar hash + extension) for the given user |
| `GET` | `https://discord.com/users/{id}/badges` | Lists the profile badges held by the given user ID |
| `GET` | `https://discord.com/users/{id}/badges/{id}` | Fetches a specific badge by badge ID for the given user |
| `GET` | `https://discord.com/users/{id}/banners/{id}.{id}` | CDN-style fetch of a specific profile banner image (banner hash + extension) for the given user |
| `GET` | `https://discord.com/users/{id}/video-filter-assets/{id}/{id}.{id}` | CDN-style fetch of a specific video-filter asset file (asset ID + hash + extension) for the given user |
| `GET` | `https://discord.com/account-standing` | Get the current user's account standing/moderation status (warnings, restrictions, strikes) |
| `GET` | `https://discord.com/acknowledgements` | Retrieve open-source/legal acknowledgements (third-party license credits) shown in the client |
| `GET` | `https://discord.com/activate` | Activate a device, license, or feature (e.g. complete a TV/console device-pairing activation) |
| `GET` | `https://discord.com/activate/handoff` | Complete a cross-device activation/handoff started on another device |
| `GET` | `https://discord.com/activity` | Singular activity resource endpoint (current/featured activity state) |
| `GET` | `https://discord.com/ads/quests` | Retrieve quest-style ad/promotional offers available to the user |
| `GET` | `https://discord.com/anteaters` | Internal/experimental endpoint (codename "anteaters"; likely a feature-flag or experiment surface) |
| `GET` | `https://discord.com/apps` | List applications (client apps listing) |
| `GET` | `https://discord.com/authorize-ip` | Authorize a new/unrecognized IP address for the account |
| `GET` | `https://discord.com/authorize-payment` | Authorize a pending payment transaction |
| `GET` | `https://discord.com/bears` | Internal/obfuscated route |
| `GET` | `https://discord.com/blog` | Discord blog content endpoint |
| `GET` | `https://discord.com/branding` | Branding/brand-asset configuration endpoint |
| `GET` | `https://discord.com/bruins` | Internal/obfuscated route |
| `GET` | `https://discord.com/build` | Application build metadata endpoint |
| `GET` | `https://discord.com/community` | Community resource or community-related listing |
| `GET` | `https://discord.com/company` | Company resource (organization/partner data) |
| `GET` | `https://discord.com/company-information` | Get company information |
| `GET` | `https://discord.com/connect/authorize` | Authorize a connect/OAuth-style connection flow |
| `GET` | `https://discord.com/creators` | Creators resource (creator program/monetization listing) |
| `GET` | `https://discord.com/disable-email-notifications` | Unsubscribe/disable the current user's email notifications |
| `GET` | `https://discord.com/disable-server-highlight-notifications` | Disable server-highlight email/notification digests for the current user |
| `GET` | `https://discord.com/discord-recruitment-scams` | Static informational/help page about Discord recruitment scams |
| `GET` | `https://discord.com/discord-xbox-offer-2020` | Landing page for the 2020 Discord–Xbox promotional offer |
| `GET` | `https://discord.com/domain-migration` | Domain-migration handler/redirect endpoint |
| `GET` | `https://discord.com/download` | Discord client download landing page |
| `GET` | `https://discord.com/download-qr-code` | Serve a QR code linking to the Discord app download |
| `GET` | `https://discord.com/downloads` | Discord client downloads page |
| `GET` | `https://discord.com/ephemeral-attachments/` | Upload/serve ephemeral (temporary) message attachments |
| `GET` | `https://discord.com/events/{id}/{id}` | Get a nested sub-resource of a guild/scheduled event by IDs |
| `GET` | `https://discord.com/external/` | Proxy/redirect handler for external (off-platform) links |
| `GET` | `https://discord.com/fallrelease` | Landing page for a Fall release promotional campaign |
| `GET` | `https://discord.com/feature/boost` | Marketing/landing page for the Server Boost feature |
| `GET` | `https://discord.com/feature/{id}` | Marketing/landing page for a named product feature by slug |
| `GET` | `https://discord.com/feature/{id}/{id}` | Marketing/landing page for a feature sub-section by slug |
| `GET` | `https://discord.com/game-shop/{id}` | Game store page for a specific game/SKU by ID |
| `GET` | `https://discord.com/gaming` | Gaming surface/landing page |
| `GET` | `https://discord.com/gauchos` | Internal/codenamed feature or campaign route ("gauchos") |
| `GET` | `https://discord.com/gifts/{id}` | Resolve a gift code's details by gift code |
| `GET` | `https://discord.com/gifts/{id}/login` | Redirect to login while resolving a gift code by code |
| `GET` | `https://discord.com/guidelines` | Fetch Discord community/usage guidelines content |
| `GET` | `https://discord.com/guild-discovery` | Fetch the guild discovery surface (discoverable/featured guilds listing) |
| `GET` | `https://discord.com/handoff` | Initiate a session handoff (transfer authenticated session between devices) |
| `GET` | `https://discord.com/icons/` | Fetch icon assets (CDN/static icon directory) |
| `GET` | `https://discord.com/index` | Fetch the application index/landing entry point |
| `GET` | `https://discord.com/inspiration` | Fetch the server-inspiration (template gallery) content |
| `GET` | `https://discord.com/invite-proxy/{id}` | Resolve an invite through the invite proxy (preview an invite by code without joining) |
| `GET` | `https://discord.com/invite/{id}` | Resolve/render an invite landing page by invite code |
| `GET` | `https://discord.com/invite/{id}/login` | Log in while accepting an invite (auth flow scoped to an invite code) |
| `GET` | `https://discord.com/invite/{id}/register` | Register a new account while accepting an invite code |
| `GET` | `https://discord.com/jobs` | Discord careers/jobs listing page |
| `GET` | `https://discord.com/licenses` | List or validate the current user's product/game licenses |
| `GET` | `https://discord.com/login` | Web app login page / authentication form |
| `GET` | `https://discord.com/login/handoff` | Cross-device login handoff endpoint to transfer an authenticated session |
| `GET` | `https://discord.com/login/one-time` | One-time login link/token consumption for passwordless or magic-link sign-in |
| `GET` | `https://discord.com/member-verification/{id}` | Fetch the membership-verification gate (rules/fields) for a guild by ID |
| `GET` | `https://discord.com/message-requests` | List or manage pending message requests (DMs awaiting acceptance) for the current user |
| `GET` | `https://discord.com/mobile` | Mobile app landing/redirect page or mobile-specific client entrypoint |
| `GET` | `https://discord.com/moderation` | Guild/community moderation dashboard or moderation API root |
| `GET` | `https://discord.com/moderation/exam` | Moderator academy/certification exam endpoint |
| `GET` | `https://discord.com/mweb-handoff` | Mobile-web to native-app session handoff endpoint |
| `GET` | `https://discord.com/newsroom` | Press/newsroom page on the marketing site |
| `GET` | `https://discord.com/nitro` | Nitro subscription landing/marketing page |
| `GET` | `https://discord.com/open-app-from-email` | Deep-link redirect that opens the native app from an email link |
| `GET` | `https://discord.com/open-source` | Open-source projects/acknowledgements page |
| `GET` | `https://discord.com/popout` | Popout window route for a detached client view (voice/stream popout) |
| `GET` | `https://discord.com/privacy` | Privacy policy page |
| `GET` | `https://discord.com/quest-home` | Client route rendering the Quests home/discovery surface |
| `GET` | `https://discord.com/quest-preview/{id}` | Client route previewing a specific Quest by its quest ID |
| `GET` | `https://discord.com/redeem` | Redeem a gift/promo/entitlement code |
| `GET` | `https://discord.com/register` | Register a new Discord user account |
| `GET` | `https://discord.com/reject-ip` | Reject/deny an unrecognized-IP login verification challenge |
| `GET` | `https://discord.com/report-review` | Review/triage a submitted report |
| `GET` | `https://discord.com/reset` | Reset account credentials (password reset entry point) |
| `GET` | `https://discord.com/rich-presence` | Rich Presence activity endpoint (set/fetch presence data) |
| `GET` | `https://discord.com/safety` | Safety/Trust-and-Safety surface root |
| `GET` | `https://discord.com/safetycenter` | Safety Center informational surface |
| `GET` | `https://discord.com/security` | Account security settings surface |
| `GET` | `https://discord.com/servers` | Server discovery/listing surface |
| `GET` | `https://discord.com/slugs` | Resolve human-readable slugs to resources |
| `GET` | `https://discord.com/snowsgiving` | Snowsgiving seasonal event surface |
| `GET` | `https://discord.com/steamlibrary/steamapps/common/` | Steam library common-apps path probe (game-detection/Steam integration) |
| `GET` | `https://discord.com/store-terms` | Fetch the store terms of sale/service |
| `GET` | `https://discord.com/streamkit` | Streamkit endpoint (StreamKit overlay/integration data for streamers) |
| `GET` | `https://discord.com/template/{id}` | Get a guild template by code/ID (legacy singular template path) |
| `GET` | `https://discord.com/template/{id}/login` | Resolve a guild template after login (apply-template-on-login flow) |
| `GET` | `https://discord.com/tos` | Get Discord Terms of Service (TOS) |
| `GET` | `https://discord.com/verification` | Account/email verification landing or flow endpoint |
| `GET` | `https://discord.com/verify` | Generic verification entry point (e.g. email/account verification link) |
| `GET` | `https://discord.com/verify-hub-email` | Verifies a Student Hub email address for the current user |
| `GET` | `https://discord.com/verify-request` | Requests/resends a verification email or token |
| `GET` | `https://discord.com/wasntme/{id}` | "Wasn't me" security action endpoint, e.g. dismissing a suspicious-login flow by token/ID |
| `GET` | `https://discord.com/welcome/{id}` | Fetches the welcome screen/invite-welcome resource for the given ID |
| `GET` | `https://discord.com/welcome/{id}/{id}` | Fetches a specific sub-resource of a welcome flow keyed by two IDs |
| `GET` | `https://discord.com/why-discord` | Marketing/static landing page route ("Why Discord") |
| `GET` | `https://discord.com/why-discord-is-different` | Marketing/static landing page route ("Why Discord Is Different") |

## CDN assets — cdn.discordapp.com/… (need a real id/hash)

| Method(s) | Endpoint (URL / path) | Meaning |
|---|---|---|
| `GET` | `https://cdn.discordapp.com/applications/{id}/app-assets/{id}.{id}` | Fetch a specific application asset image by asset ID/format |
| `GET` | `https://cdn.discordapp.com/applications/{id}/app-icons/{id}.png` | Fetch a specific application icon image (PNG) |
| `GET` | `https://cdn.discordapp.com/avatar-decoration-presets/{id}.{id}` | Fetch an avatar-decoration preset asset (CDN-style by asset ID) |
| `GET` | `https://cdn.discordapp.com/avatars/{id}/archived/{id}/{id}.{id}` | Fetch an archived user avatar image asset |
| `GET` | `https://cdn.discordapp.com/badge-icons/{id}.png` | Fetch a profile/guild badge icon image by ID |
| `GET` | `https://cdn.discordapp.com/emojis/{id}.{id}` | CDN-style emoji image asset by emoji ID and file extension/variant |
| `GET` | `https://cdn.discordapp.com/guild-events` | List/fetch guild scheduled events surfaced across discovery |
| `GET` | `https://cdn.discordapp.com/guild-events/{id}/images/{id}.{id}` | Fetch a specific cover image asset (by hash/extension) for a guild scheduled event |
| `GET` | `https://cdn.discordapp.com/roles/{id}/icons/{id}.png` | Fetch a guild role's icon image (PNG) by role ID and icon hash |
| `GET` | `https://cdn.discordapp.com/soundboard-sounds/{id}` | Fetch a soundboard sound by its ID |
| `GET` | `https://cdn.discordapp.com/templates/{id}/icons/{id}.{id}` | Get a template's guild icon image asset (template ID, icon hash, file extension) |

## Internal / dev-build endpoints — discord.com/__development/*

Staff/dev build-override tooling; last two are dev/canary-only.

| Method(s) | Endpoint (URL / path) | Meaning |
|---|---|---|
| `GET` | `https://discord.com/__development/build_overrides` | List active client build overrides (staff/dev build-override tool) |
| `POST` | `https://discord.com/__development/create_build_override_link` | Create a shareable link that applies a specific client build override |
| `GET` | `https://discord.com/__development/link` | Apply a build override from a link token (needs query params) |
| `POST` | `https://discord.com/__development/source_maps` | Submit/serve minified client source maps (dev-build error symbolication) |
| `?` | `https://discord.com/__development/staff_dev_tools/version` | Staff dev-tools client version (dev/canary build only — 404 on production) |
| `?` | `https://discord.com/_discord/join` | Internal invite/join handoff (dev-build only — 404 on production) |

## Bundle noise — filesystem strings, not endpoints (path shown for reference)

| Method(s) | Endpoint (URL / path) | Meaning |
|---|---|---|
| `—` | `discord.com/app/bin` | Serve an application binary/installer asset |
| `—` | `discord.com/dev/null` | Unix null device path constant (bundled string, not a Discord endpoint) |
| `—` | `discord.com/dev/poll` | Unix poll device path constant (bundled string, not a Discord endpoint) |
| `—` | `discord.com/dev/shm` | Unix shared-memory device path constant (bundled string, not a Discord endpoint) |
| `—` | `discord.com/dev/shm/tmp` | Unix shared-memory temp path constant (bundled string, not a Discord endpoint) |
| `—` | `discord.com/dev/stderr` | Unix standard-error device path constant (bundled string, not a Discord endpoint) |
| `—` | `discord.com/dev/stdin` | Unix standard-input device path constant (bundled string, not a Discord endpoint) |
| `—` | `discord.com/dev/stdout` | Unix standard-output device path constant (bundled string, not a Discord endpoint) |
| `—` | `discord.com/dev/tty` | Unix controlling-terminal device path constant (bundled string, not a Discord endpoint) |
| `—` | `discord.com/dev/tty1` | Unix first virtual terminal device path constant (bundled string, not a Discord endpoint) |
| `—` | `discord.com/api{id}` | Dynamically-segmented internal API base/version resolver |
| `—` | `discord.com/assets/` | Serve static client assets (JS/CSS/images) |
| `—` | `discord.com/proc` | Likely a probe/path-traversal test target mirroring the Linux /proc filesystem root |
| `—` | `discord.com/proc/self` | Likely a probe/path-traversal test target mirroring /proc/self (current process info) |
| `—` | `discord.com/proc/self/fd` | Likely a probe/path-traversal test target mirroring /proc/self/fd (process file descriptors) |

## Dead / unresolved — 404 at both bases (path shown; removed / bare root / fragment)

| Method(s) | Endpoint (URL / path) | Meaning |
|---|---|---|
| `—` | `discord.com/applications/trending/global (404 at /api/v9 + web)` | List globally trending applications |
| `—` | `discord.com/archive/privacy/june-2020 (404 at /api/v9 + web)` | Retrieve the archived June 2020 privacy policy document |
| `—` | `discord.com/archive/terms/may-2020 (404 at /api/v9 + web)` | Retrieve the archived May 2020 terms of service document |
| `—` | `discord.com/billing (404 at /api/v9 + web)` | Billing root/overview endpoint |
| `—` | `discord.com/channels (404 at /api/v9 + web)` | Channels root/collection endpoint |
| `—` | `discord.com/dev (404 at /api/v9 + web)` | Developer resource/portal root |
| `—` | `discord.com/family-center/my-family (404 at /api/v9 + web)` | Get the current user's linked family members in Family Center |
| `—` | `discord.com/family-center/settings (404 at /api/v9 + web)` | Get/update Family Center settings for the current user |
| `—` | `discord.com/new/download (404 at /api/v9 + web)` | App download page on the marketing site |
| `—` | `discord.com/new/guidelines (404 at /api/v9 + web)` | Community guidelines page on the marketing site |
| `—` | `discord.com/new/jobs (404 at /api/v9 + web)` | Careers/jobs page on the marketing site |
| `—` | `discord.com/new/safety (404 at /api/v9 + web)` | Safety center page on the marketing site |
| `—` | `discord.com/new/terms (404 at /api/v9 + web)` | Terms of service page on the marketing site |
| `—` | `discord.com/streams (404 at /api/v9 + web)` | Go-Live stream operations (manage current user's voice-channel stream) |
| `—` | `discord.com/terms/back-to-school-2020/instagram (404 at /api/v9 + web)` | Terms/rules page for the Back-to-School 2020 Instagram promotion |
| `—` | `discord.com/terms/back-to-school-2020/twitter (404 at /api/v9 + web)` | Terms/rules page for the Back-to-School 2020 Twitter promotion |
| `—` | `discord.com/terms/snowsgiving-2020/instagram (404 at /api/v9 + web)` | Terms/rules page for the Snowsgiving 2020 Instagram promotion |
| `—` | `discord.com/terms/snowsgiving-2020/twitter (404 at /api/v9 + web)` | Terms/rules page for the Snowsgiving 2020 Twitter promotion |
| `—` | `discord.com/user-offers (404 at /api/v9 + web)` | List the promotional offers available to the current user |
| `—` | `discord.com/user-offers/reverse-trial (404 at /api/v9 + web)` | Manage the current user's reverse-trial offer (Nitro reverse-trial enrollment) |
| `—` | `discord.com/users (404 at /api/v9 + web)` | User lookup/operations collection (e.g. find/query users) |
| `—` | `discord.com/b5nqj (404 at /api/v9 + web)` | Obfuscated/internal short-code route (likely tracking or experiment beacon) |
| `—` | `discord.com/changelogs/@me/messages (404 at /api/v9 + web)` | Fetch changelog messages for the current user |
| `—` | `discord.com/college (404 at /api/v9 + web)` | College/student verification or hub resource |
| `—` | `discord.com/cp93l (404 at /api/v9 + web)` | Short-code/static asset or redirect resource |
| `—` | `discord.com/debug/applied-boosts/ends-at (404 at /api/v9 + web)` | Get the end time of applied debug/test boosts |
| `—` | `discord.com/dev-newsletter (404 at /api/v9 + web)` | Subscribe to or manage the developer newsletter |
| `—` | `discord.com/error-reporting-proxy/web (404 at /api/v9 + web)` | Proxy endpoint for forwarding web-client error reports |
| `—` | `discord.com/game-invite/@me (404 at /api/v9 + web)` | List the current user's active game invites |
| `—` | `discord.com/giphy (404 at /api/v9 + web)` | Giphy GIF provider integration surface |
| `—` | `discord.com/home (404 at /api/v9 + web)` | Fetch the user's home/landing surface |
| `—` | `discord.com/home/web_user (404 at /api/v9 + web)` | Fetch the home surface for a web (logged-in) user |
| `—` | `discord.com/hypesquad (404 at /api/v9 + web)` | Get/manage the user's HypeSquad membership |
| `—` | `discord.com/hypesquad-riot (404 at /api/v9 + web)` | Get/manage HypeSquad participation for a Riot (Events) program |
| `—` | `discord.com/icymi (404 at /api/v9 + web)` | Fetch the "In Case You Missed It" recap/digest feed |
| `—` | `discord.com/integrations (404 at /api/v9 + web)` | List the current user's third-party integrations/connections |
| `—` | `discord.com/k52hw (404 at /api/v9 + web)` | Short-link/invite-style code resolver that redirects a vanity short code to its target resource |
| `—` | `discord.com/klipy (404 at /api/v9 + web)` | Klipy GIF/clip-search integration endpoint or partner asset proxy |
| `—` | `discord.com/league-communities (404 at /api/v9 + web)` | List or resolve League of Legends / game-community guild associations |
| `—` | `discord.com/newsletter (404 at /api/v9 + web)` | Newsletter subscription signup endpoint/page |
| `—` | `discord.com/okjv0 (404 at /api/v9 + web)` | Short-link/invite-style code resolver that redirects a vanity short code to its target resource |
| `—` | `discord.com/one-time (404 at /api/v9 + web)` | One-time token/link consumption endpoint (e.g. passwordless or single-use action) |
| `—` | `discord.com/playground (404 at /api/v9 + web)` | Developer playground / interactive API or component sandbox page |
| `—` | `discord.com/ptb (404 at /api/v9 + web)` | Public Test Build client web route (PTB release channel landing), not a REST data endpoint |
| `—` | `discord.com/quest-preview (404 at /api/v9 + web)` | Client route rendering a generic Quest preview surface |
| `—` | `discord.com/reject-mfa (404 at /api/v9 + web)` | Reject/deny a pending MFA login verification request |
| `—` | `discord.com/rpc (404 at /api/v9 + web)` | Local RPC server endpoint for client/Game SDK communication |
| `—` | `discord.com/tenor (404 at /api/v9 + web)` | Tenor GIF proxy/search endpoint (Discord's Tenor integration) |
| `—` | `discord.com/tmp (404 at /api/v9 + web)` | Temporary/internal scratch endpoint (non-public build artifact) |
| `—` | `discord.com/tutorial/indicators (404 at /api/v9 + web)` | List the current user's in-app tutorial indicators (onboarding hints state) |
| `—` | `discord.com/user-offer-ids (404 at /api/v9 + web)` | List the offer IDs available/applicable to the current user |
| `—` | `discord.com/usr/bin (404 at /api/v9 + web)` | Non-API filesystem path captured in the bundle; not a Discord endpoint |
| `—` | `discord.com/usr/local/bin (404 at /api/v9 + web)` | Non-API filesystem path captured in the bundle; not a Discord endpoint |
| `—` | `discord.com/var (404 at /api/v9 + web)` | Non-API filesystem path captured in the bundle; not a Discord endpoint |
| `—` | `discord.com/warframe (404 at /api/v9 + web)` | Game/partner-specific landing or integration path (Warframe) |
