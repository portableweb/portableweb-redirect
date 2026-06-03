# portableweb

Installs the [PortableWeb CLI](https://github.com/portableweb/cli) under the friendly package name `portableweb`.

```bash
npm install -g portableweb
```

This gives you two commands:

```bash
pweb --help
portableweb --help
```

Both are identical — `pweb` is the short form, `portableweb` is the long form.

---

## What this package is

This is a thin redirect package. All CLI logic lives in [`@portableweb/cli`](https://www.npmjs.com/package/@portableweb/cli). This package simply declares it as a dependency and re-exports its bin so you can install without the npm scope.

| Install command | Same result |
|---|---|
| `npm install -g portableweb` | ✓ |
| `npm install -g @portableweb/cli` | ✓ |

---

## Commands

See the full command reference in the [`@portableweb/cli` README](https://github.com/portableweb/cli#readme):

| Command | Description |
|---|---|
| `pweb init [dir]` | Scaffold a new `.pweb` project |
| `pweb pack [source] [-o output]` | Pack a directory into a `.pweb` bundle |
| `pweb unpack <file> [-o dir]` | Extract a `.pweb` bundle |
| `pweb validate <file>` | Validate a `.pweb` bundle against the spec |
| `pweb open-lite <file>` | Open a `.pweb` in a native viewer (macOS only) |
