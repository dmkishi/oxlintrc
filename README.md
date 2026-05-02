@dmkishi/oxlintrc
================================================================================
DM Kishi's custom oxlint config file.

Install
--------------------------------------------------------------------------------
```sh
pnpm add --save-dev oxlint oxlint-tsgolint @dmkishi/oxlintrc
touch .oxlintrc.json
```

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

Changelog
--------------------------------------------------------------------------------
### v0.0.0 (2026-5-4)
- Initial release.
