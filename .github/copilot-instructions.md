# Copilot Instructions for Broadcast-8.0.0-by-Solstar

## Project Overview
This is a Shopify theme codebase. It is organized into key folders:
- `assets/`: JavaScript and CSS for interactive features and styling
- `blocks/`, `sections/`, `snippets/`, `templates/`: Liquid files for Shopify theme structure and dynamic content
- `config/`: Theme configuration and settings
- `locales/`: Localization files for multi-language support
- `layout/`: Base layout Liquid files

## Architecture & Patterns
- **Liquid-Driven UI**: Most UI logic is in Liquid files (`sections/`, `blocks/`, `snippets/`). JavaScript in `assets/` enhances interactivity.
- **Theme Customization**: `config/settings_schema.json` and `config/settings_data.json` define theme settings and data. Changes here affect theme options in Shopify admin.
- **Localization**: Add or update translation keys in `locales/` for multi-language support.
- **Asset Management**: JS/CSS in `assets/` is loaded via Liquid tags in layout/section files. Use descriptive filenames and keep logic modular.

## Developer Workflows
- **No build step required**: Most changes are live-editable. For advanced asset management, use Shopify CLI or Theme Kit (not present by default).
- **Previewing**: Upload theme to Shopify store for live preview. Use Shopify's theme editor for settings.
- **Debugging**: Use browser dev tools for JS/CSS. Liquid errors show in Shopify preview.
- **Version Control**: Use Git for source management. Branching follows feature/topic naming (e.g., `hide-cart-icon-on-header`).

## Conventions & Best Practices
- **Liquid Naming**: Use kebab-case for files and variables. Keep sections/blocks modular and reusable.
- **JS Patterns**: Each feature JS file in `assets/` should be self-contained. Avoid global variables; use IIFEs or modules.
- **CSS**: Theme styles in `theme.css`, component styles in separate files. Avoid inline styles in Liquid.
- **Localization**: Always update all language files for new keys.
- **Settings**: Document new settings in `settings_schema.json`.

## Integration Points
- **Shopify APIs**: AJAX calls in JS (e.g., cart, product info) interact with Shopify endpoints. See `assets/cart-bar.js`, `assets/product-info.js` for examples.
- **External Libraries**: Some assets use third-party JS (e.g., Photoswipe, Rellax). Keep vendor code in `assets/vendor.js` or separate files.

## Key Files & Directories
- `assets/theme.js`, `assets/theme.dev.js`: Main JS entry points
- `sections/header.liquid`, `sections/footer.liquid`: Core layout components
- `config/settings_schema.json`: Theme settings structure
- `locales/en.default.json`: Base language file

## Example Patterns
- To add a new section: create a `.liquid` file in `sections/`, update `settings_schema.json` if settings are needed.
- To add a JS feature: create a new file in `assets/`, reference it in the relevant Liquid file.
- To support a new language: duplicate a file in `locales/` and translate keys.

---
For questions or unclear conventions, ask for clarification or review recent commits for examples.
