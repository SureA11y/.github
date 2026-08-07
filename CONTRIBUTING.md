# Contributing

This applies to every repository in the SureA11y organization that does not
carry its own `CONTRIBUTING.md`. [`@surea11y/core`](https://github.com/SureA11y/core)
has its own, covering rule authoring and the engine's non-negotiables — read
that one before touching a rule.

## Before opening a pull request

Run the test suite and make sure it is green. Keep commits focused, one logical
change each, with a message explaining *why* — the diff already shows what.

The framework bindings are deliberately thin. Logic that decides *whether
something is an accessibility violation* belongs in the engine, not in an
adapter; a binding's job is to hand over a DOM and format what comes back. A
change that moves that decision into a binding will be refused even when it
works, because it would make two packages disagree about the same page.

## Sign-off

Contributions are accepted under the
[Developer Certificate of Origin](https://developercertificate.org/) — a short
statement that you wrote the patch, or otherwise have the right to submit it
under the project's license. Sign off with `-s`:

```sh
git commit -s -m "..."
```

which appends a `Signed-off-by:` line from your git `user.name` and
`user.email`. Please use a real name.

There is no CLA.

## Reporting a bug

Open an issue in the repository the problem is in — the binding's repo for
adapter behaviour, [`core`](https://github.com/SureA11y/core) for anything about
what a rule decides. Include the versions of both packages and, where possible,
a minimal HTML fixture. Output is deterministic, so a fixture usually settles a
question faster than a description of it.
