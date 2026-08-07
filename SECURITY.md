# Security policy

This policy covers every repository in the SureA11y organization that does not
carry its own `SECURITY.md`. [`@surea11y/core`](https://github.com/SureA11y/core)
has its own, which additionally documents the engine's threat surface.

## Reporting a vulnerability

Report privately rather than opening a public issue — email
rumoroso.a11y@gmail.com with a description and, if possible, a minimal
reproduction.

You can expect an acknowledgement within five working days. These are
solo-maintained projects, so please allow 90 days from that acknowledgement
before public disclosure, and get in touch again if you haven't heard back.

There is no bug bounty program.

## Supported versions

Only the latest published version of each package receives security fixes.

## Scope

The framework bindings are thin adapters: they hand a DOM to
[`@surea11y/core`](https://github.com/SureA11y/core) and format what comes back.
They make no network requests of their own and execute no page content. A
vulnerability in scanning behaviour itself most likely belongs in the core
repository.
