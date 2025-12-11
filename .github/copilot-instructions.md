# Copilot Instructions for EazyAutodelete Translations

## Repository Overview

This repository contains translations for the EazyAutodelete Discord bot. Translations are managed through Weblate (https://translate.eazyautodelete.xyz/) and stored in this repository for version control and distribution.

## Repository Structure

- **`/commands/`** - Translation files for bot commands
- **`/dashboard/`** - Translation files for the web dashboard
- **`/website/`** - Translation files for the website
- **`*.tbx` files** - Terminology database files in TBX format (XML-based translation memory)
- **`README.md`** - Documentation for translators

## File Formats

### JSON Translation Files
- Translation files use JSON format with key-value pairs
- Keys are English identifiers, values are translated strings
- Structure: `{ "key": "translated text with %s placeholders" }`
- Language codes follow ISO 639-1 (e.g., `en.json`, `de.json`, `pt_BR.json`)

### TBX Files
- TBX (TermBase eXchange) files are XML-based terminology databases
- These files follow the MARTIF standard (ISO 12200)
- Currently used as placeholders for language support

## Translation Guidelines

### Formatting Rules
1. **Placeholders**: `%s` is used as a placeholder that will be replaced with dynamic values
   - Never translate or remove `%s` placeholders
   - Maintain the order and count of placeholders
   
2. **Markdown Formatting**: Translations may contain Discord markdown
   - `**text**` = bold text
   - `[text](url)` = hyperlinks (preserve spacing exactly)
   - `/command` = command names (do NOT translate)
   
3. **Special Characters**: Preserve special characters and spacing
   - Line breaks (`\n`) must be maintained
   - Backticks (`) for code/technical terms
   - Asterisks (*) for emphasis

### Key Principles
- **Consistency**: Use consistent terminology across all translations
- **Context**: Consider the Discord bot context when translating
- **Completeness**: All keys in `en.json` should have corresponding translations
- **Format Preservation**: Maintain the JSON structure and formatting

## Weblate Integration

- This repository is synchronized with Weblate translation platform
- Translators work in Weblate, changes are pushed here automatically
- Direct edits to translation files should be minimal and careful
- The primary workflow is: Translators → Weblate → This Repository

## Important Conventions

1. **Language Codes**
   - Use standard ISO 639-1 codes (2 letters)
   - Regional variants use underscore: `pt_BR` (Portuguese - Brazil)
   
2. **File Naming**
   - All translation files: `{language_code}.json`
   - TBX files: `{language_code}.tbx`
   
3. **JSON Structure**
   - Use 4 spaces for indentation
   - Keep keys in alphabetical order when possible
   - No trailing commas

## When Making Changes

### Adding New Languages
1. Create JSON files in `/commands/`, `/dashboard/`, and `/website/` directories
2. Create corresponding TBX file in root directory
3. Use existing language files as templates
4. Coordinate with Weblate admins for platform integration

### Updating Translations
- Prefer making changes through Weblate when possible
- If editing directly, ensure JSON validity
- Maintain formatting consistency with existing files
- Test placeholders and formatting after changes

### Code Quality
- Validate JSON syntax before committing
- Ensure all translation files have matching keys
- Preserve the structure and order of keys from `en.json` files
- Run any available validation scripts before submitting changes

## Testing Changes

When working with this repository:
1. Validate JSON syntax: `python -m json.tool file.json`
2. Check for missing keys by comparing with `en.json`
3. Verify placeholder counts match the English version
4. Ensure markdown formatting is preserved

## Don't Do

- Don't translate command names (e.g., `/help`, `/language`)
- Don't modify placeholder syntax `%s`
- Don't change the structure or order of JSON significantly without coordination
- Don't remove keys from translation files
- Don't add translations that aren't requested through Weblate
