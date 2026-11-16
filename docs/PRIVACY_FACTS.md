# Privacy evidence and publication gaps

Reviewed 2026-11-15. App: /Users/azamat/Projects/MayakiOSApp (SQLite migration through b3ba7a1); site: /Users/azamat/Projects/MayakSite. Source inspection is not verification of a live deployment or a signed release. No credentials, keys or user history inspected.

## Confirmed source evidence

| Public statement | Evidence in app repository | Limit |
| --- | --- | --- |
| XMPP client, provider hosts accounts | AppEnvironment, XMPPFrameworkClient, onboarding; owner instruction | Do not promise federation with every server |
| Local history uses iOS protection, no blanket app-level DB encryption | SQLiteMessageRepository, MigratingMessageRepository, AtomicHistoryStore | Sealed notes/journal differ; do not call all data plaintext or all data encrypted |
| Pre-migration copy retained | MigratingMessageRepository and SQLITE_MIGRATION_PLAN.md | Active deletion is not erasure from old copies; disclosure retained on policy page |
| Passwords/OMEMO state shared locally with NSE | SharedStoreScopeResolver, KeychainSecureStorage, NotificationService | Not a promise that all metadata stays on device |
| Push request has metadata beyond token | infrastructure/push/source/fpush/src/xmpp/message_loop.rs reads from/to IQ; token/module parser | Account-server payload contents and deployed logging require verification |
| Generated APNs alert is neutral; extension fetches content | infrastructure/push/source/fpush-apns/src/push.rs, NotificationService | additional_data is configurable; verify deployed config before promising no content in APNs; do not claim sandbox-only from obsolete docs |
| Google STUN fallback exists | WebRTCCallMediaEngine.swift: stun.l.google.com | TURN presence does not itself guarantee peer IP anonymity |
| Link previews default off | SecuritySettingsView and ConversationView privacy.linkPreviews | Requests disclose IP to destination; do not promise all network requests stay local |
| Location and media actions use system permissions | Info.plist, location/media features | Selected data is transmitted when user sends it |
| No third-party ad/analytics SDK found in inspected source | dependency/source review; SECURITY.md | Recheck final bundled dependencies; Apple diagnostics separate |
| Diagnostic logging opt-in for Release | SECURITY.md and PresenceDebug | Hashed identifiers are pseudonymous, not necessarily anonymous |
| App policy/support links not configured | AppSettingsView.swift AppLinks nil | Must be configured in app before submission |

## Removed or corrected claims

- “All formats”, “full iOS integration”, “one gesture”, “progressive download”, per-account sound/privacy promises: removed unsupported precision from homepage.
- “Upload server cannot see content”: key distribution matters; unencrypted message with the file key defeats that assertion for the message server.
- “Push receives only token/module”: service also receives XMPP addressing/connection metadata.
- “TURN hides IP”: not guaranteed without relay-only routing and appropriate candidate handling.
- “All permissions operate only locally”: sending media/location and calling necessarily transmits selected data.
- “Anonymous diagnostics”: replaced by technical events/transformed identifiers.
- “Sign-out deletes everything”: no universal promise; retained migration copies and downloads disclosed.
- “No infrastructure”: Mayak does not host user XMPP accounts, but has an auxiliary push service.

## Owner fields — deliberately unresolved

Owner asked to fill later. No fake identity/email/provider/retention was inserted. Public drafts use `data-publish-blocker` fields for:
- identity and working support/privacy contact;
- push host/country, logs, rate-limit state, backups, retention/deletion;
- website host/country and request-log retention/access;
- support provider and message/attachment retention/deletion.

These must become actual operating practices, not aspirational statements. Review applicable regional obligations and protections of service providers. Do not promise equivalent third-party safeguards without validating them. For independent XMPP providers, explain user choice and provider-specific policies.

## Apple and reference sources

- https://developer.apple.com/app-store/review/guidelines/ — 1.5 contact, 5.1.1 policy in app and metadata; data/uses/recipients, retention/deletion, permissions.
- https://developer.apple.com/help/app-store-connect/reference/app-information/platform-version-information — Support URL must lead to actual contact information.
- https://developer.apple.com/help/app-store-connect/manage-app-information/manage-app-privacy/ — required policy URL and accurate privacy disclosures.
- https://monal-im.org/privacyarchive/monal_app_rev_003/ — structural reference: distinguish client, account server, push, calls and diagnostics. Mayak text is independently written from its code; no Monal operator, infrastructure or retention copied.

## Verification boundary

No deployment, live mail delivery, VPS logs/configuration, final App Store privacy questionnaire or device release validated here. Static link validation is not publication readiness while owner fields remain. Update this file when those facts are confirmed.

## Demo contact update

At the owner’s request, support/privacy pages now show “Mayak team” and reserved `.example` email addresses for layout review. These are explicitly labelled demo data, not a verified legal identity or functioning support channel. Other hosting/retention fields remain unresolved.

## GitHub Pages preparation

2026-11-15: explicit relative index.html links support file:// and GitHub project subpaths. Python checker removed at owner request; no runtime/build dependencies. Manual Pages workflow uploads only public HTML/assets. Demo markers remain visible but do not block preview deployment. No live deployment performed.

## 2026-11-16 revision — app cb01b9f

RU/EN policy rewritten around no Mayak-hosted conversation archive, not a blanket no-processing claim. Support address supplied by owner: support@mayakapp.site. Owner intends no support archive and deletion after processing; mailbox provider/copies remain unverified. Owner wishes push logging disabled; NOT verified on live host. Repository compose currently uses local log driver, 2 × 2 MB rotation. No server configuration changed. fpush tokenblocker/rate limiter use in-memory token state; expiry of blocking does not prove removal of the map entry. Provider IQ publisher may be a bare JID, not domain-only. Neutral APNs payload is source-verified; deployed additional_data unverified. AccountDataCleanup now cleans active and old account history, with incomplete-cleanup errors; individual message deletion and exports remain separate.

Responsible person's identity was supplied privately, but user questioned publication: not inserted. Remaining publication facts are visibly grouped in one notice, not silently treated as resolved. Mail delivery, hosting location, live logs, service-state lifetime and mail-provider retention require confirmation. No claim of legal clearance or production deployment. Monal used only as a structural reference; no infrastructure/retention promises copied.

Public-page cleanup (2026-11-16): removed the entire pre-publication verification notice from RU/EN policy at owner request. Outstanding infrastructure/retention/identity checks above remain unresolved internal release checks; removing the public notice does not verify them. No no-logs or zero-retention promise added.
