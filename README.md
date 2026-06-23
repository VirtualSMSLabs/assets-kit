# Assets Kit

Ready-to-use image assets for applications integrating with the [virtualsms.de](https://virtualsms.de) API. All assets are free to use in your applications.

## Getting Started

There are three ways to use these assets:

1. **Direct link** — Reference files directly from this repository:
   ```
   https://github.com/VirtualSMSLabs/assets-kit/blob/main/app_logos/wa.webp
   ```
2. **Download** — Grab the zip bundles from the [latest release](https://github.com/VirtualSMSLabs/assets-kit/releases):
   - `app_logos.zip` — all service logos
   - `country_flags.zip` — all country flags
3. **Self-host** — Download and host the assets on your own infrastructure.

## Folders

### `app_logos/`

Service logos keyed by the `standardCode` from the virtualsms.de API. Each file is named `{standardCode}.webp` (e.g., `wa.webp` for WhatsApp, `tg.webp` for Telegram).

**Coverage:** 280 of 2,034 services (13.8%) currently have logos. We are actively working to provide logos for the remaining services.

### `country_flags/`

Country flags keyed by their country code (e.g., `ar.webp` for Argentina, `us.webp` for United States).

## Fallback

A `coming_soon.webp` placeholder is included in `app_logos/`. Use it as a fallback image for services that do not yet have a dedicated logo:

```
/assets/app_logos/coming_soon.webp
```

## Usage Example

Call the virtualsms.de API to get the list of available services:

```
https://api.virtualsms.de/stubs/handler_api?action=getServicesList&country=39&api_key=YOUR_API_KEY
```

Response:

```json
{
  "status": "success",
  "services": [
    {
      "code": "tg",
      "name": "Telegram"
    },
    {
      "code": "wa",
      "name": "WhatsApp"
    }
  ]
}
```

Use the returned `code` (the `standardCode`) to build the logo path:

```
/assets/app_logos/tg.webp   → Telegram
/assets/app_logos/wa.webp   → WhatsApp
```

All images are in `.webp` format.
