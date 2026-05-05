@dmkishi/oxlintrc
================================================================================
DM Kishi's custom oxlint config file.

Install
--------------------------------------------------------------------------------
```sh
pnpm add --save-dev @dmkishi/oxlintrc oxlint oxlint-tsgolint
touch .oxlintrc.json
```

### .oxlintrc.json
```json
{
  "$schema": "./node_modules/oxlint/configuration_schema.json",
  "extends": ["./node_modules/@dmkishi/oxlintrc/.oxlintrc.json"],
  "rules": {
    // Local overrides
  },
  "options": {
    "typeAware": true, // Enable rules that require type information
    "typeCheck": true // Enable experimental type checking
  }
}
```

Develop
--------------------------------------------------------------------------------
### Validation
The validation script `pnpm validate` provides basic validation of the config
file using Oxlint itself to load, parse, and resolve the config file. It errors
on malformed JSON and schema violations including wrong types, rule-name
mistakes, bad category names.

**Note**: Oxlint writes errors to stdout, not stderr, so outputs are captured
and printed only on error.

Changelog
--------------------------------------------------------------------------------
### v0.0.1 (2026-5-5)
- Fix incorrect path to config file in `package.json`.
- Restore hanging commas in config file.
- Add validation:
  - Add validation script.
  - Add validation script to Husky script.
  - Run Husky script on publish.
- Etc.

### v0.0.0 (2026-5-4)
- Initial release.
