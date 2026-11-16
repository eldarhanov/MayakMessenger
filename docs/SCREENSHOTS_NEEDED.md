# Screenshots needed for the public site

The repository contains no publishable app screenshots (icon artwork only).
Until real captures exist, the homepage uses a text composition with the
app icon — no fabricated UI is shown.

When capturing, use demo accounts and synthetic content only; no real JIDs,
avatars, names or message text.

Suggested set (en-US + ru-RU, light and dark):

| File | Screen | Shows |
|---|---|---|
| `home-chats-*.png` | Chat list | folders, unread badges, search |
| `home-conversation-*.png` | Conversation | bubbles, media, composer |
| `home-call-*.png` | Active video call | CallKit/system UI |
| `home-stickers-*.png` | Sticker picker | animated packs |
| `home-settings-*.png` | Notification/appearance settings | accent choice, privacy options |
| `privacy-lock-*.png` | App lock / security settings | fingerprint verification |

Place captures in `website/assets/screens/` (optimised, ≤ ~400 KB each,
explicit width/height) and reference them from the homepage sections.
