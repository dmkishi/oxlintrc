@dmkishi/oxlintrc
================================================================================
DM Kishi's custom oxlint config file.

Install
--------------------------------------------------------------------------------
### Add packages
```sh
pnpm add --save-dev @dmkishi/oxlintrc oxlint oxlint-tsgolint
```

### Add `.oxlintrc.json`
Create `.oxlintrc.json` and copy in below.
```json
{
  "$schema": "./node_modules/oxlint/configuration_schema.json",
  "extends": ["./node_modules/@dmkishi/oxlintrc/.oxlintrc.json"],
  "rules": {
    // Local overrides
    /* Pedantic ************************************************************* */
    /* Style **************************************************************** */
    /* Perf ***************************************************************** */
  },
  "options": {
    "typeAware": true, // Enable rules that require type information
    "typeCheck": true // Enable experimental type checking
  }
}
```

### Add lint command to `package.json`
```json
"lint": "oxlint"
```

Run it: `pnpm lint`

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
### v0.4.0 (2026-9-6)
- Add rules.
- Etc.: Improve README and update deps.

### v0.3.0 (2026-5-19)
- Disable `typescript/prefer-readonly-parameter-types`. Agree in theory but too
  noisy. Too many legitimate readonly types are flagged as mutable due to the
  rule's strict internal model, e.g. `HTMLElement`, `Date`, `AbortSignal`, etc.
  Disables the rule rather than maintaining an ever-growing allowlist.

### v0.2.1 (2026-5-15)
- Fix `prefer-readonly-parameter-types` allowlist with comment-explanation.

### v0.2.0 (2026-5-15)
- Add `Response` as exception to `typescript/prefer-readonly-parameter-types`.
- Update dep: `oxlint`.

### v0.1.0 (2026-5-7)
- Add `AbortSignal` as exception to `typescript/prefer-readonly-parameter-types`.
- Improve styles.

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
