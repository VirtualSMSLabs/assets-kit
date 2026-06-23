# Assets Kit contribution guide

## Contributing Logos

We welcome contributions of missing service logos!

### Guidelines

- **Format:** `.webp` (lossy preferred, quality 90+)
- **Size:** 64×64px or 128×128px square
- **Background:** Transparent
- **Margin:** Minimal padding — logo should fill most of the canvas
- **Filename:** Must match the `standardCode` from `services.json` exactly (e.g., `wa.webp`, `tg.webp`)

### How to Find the Correct Code

1. Call the virtualsms.de API:
   ```
   https://api.virtualsms.de/stubs/handler_api?action=getServicesList&api_key=YOUR_API_KEY
   ```
2. Find the service you want to contribute a logo for
3. Use the returned `code` value as the filename

### Submission

1. Fork this repository
2. Add your `.webp` file to the appropriate folder (`app_logos/` or `country_flags/`)
3. Open a Pull Request with the title: `add logo: {standardCode} - {serviceName}`

### Metadata

All images must have EXIF/XMP/ICC profiles stripped before submission.

```sh
# Strip metadata with ImageMagick
magick input.png +profile "*" output.webp
```

## Reporting Issues

Use the [issue template](.github/ISSUE_TEMPLATE/asset_request.md) to:
- Request a logo for a missing service
- Report incorrect or outdated logos
- Report incorrect country flags
