# portableweb (redirect package) — Claude Context

## What this is

A thin npm redirect package published under the unscoped name `portableweb`. Its only purpose is to let users install the CLI with:

```bash
npm install -g portableweb
```

instead of the scoped name `@portableweb/cli`. It declares `@portableweb/cli` as a dependency and re-exports its bin via `bin/pweb.js`.

## Structure

```
portableweb-redirect/
  package.json      # name: "portableweb", depends on @portableweb/cli
  bin/pweb.js       # one-liner: require("@portableweb/cli")
```

## How it works

`bin/pweb.js` simply `require`s `@portableweb/cli`, which runs that package's `dist/index.js` entry point. No logic lives here.

## What not to change

- Do not add any logic to `bin/pweb.js` — all CLI code lives in `@portableweb/cli`.
- Keep the version of `@portableweb/cli` in `dependencies` in sync with releases. The range `^0.1.0` picks up patch/minor bumps; bump the floor when a new major/minor is released.
- The two bin names (`pweb` and `portableweb`) must match those declared in `@portableweb/cli/package.json`.

## Relation to other packages

- `../cli/` (`@portableweb/cli`) — the real CLI this package wraps.
- These two packages should always be released together. When `@portableweb/cli` cuts a new version, update the dependency here and publish `portableweb` with a matching version bump.
