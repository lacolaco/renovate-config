# renovate-config

This repository hosts several opinionated [Renovate](https://www.whitesourcesoftware.com/free-developer-tools/renovate) config presets.

## Usage

Renovate can resolve GitHub-hosted config preset using `github>` directive. Please read more at [Shareable Config Presets \| Renovate Docs](https://docs.renovatebot.com/config-presets/#preset-hosting).

Presets hosted in this repository can be resolved as the following:

```json
{
  "extends": ["config:base", "github>lacolaco/renovate-config:presetName"]
}
```

If `:presetName` is omitted, `default` is used instead. `default.json` includes all presets.

## Presets

- `lacolaco/renovate-config:automerge-types`
  - Enable automerge of `@types` package's minor updates.
- `lacolaco/renovate-config:ng-update`: For Angular CLI-based repository
  - Disable major or minor version updates for packages which are under the control from `ng update` commands.
    - `@angular/core` package group: https://github.com/angular/angular/blob/master/tools/defaults.bzl#L27
    - `@angular/cli` package group: https://github.com/angular/angular-cli/blob/master/packages/angular/cli/package.json
    - `@angular/material` package group: https://github.com/angular/components/blob/master/src/material/package.json
    - `typescript` 
    - `rxjs` (major version only is disabled)
- `lacolaco/renovate-config:angular-eslint`
  - Add groups for `@angular-eslint` and `@typescript-eslint` packages (no automerge).

## License

MIT
