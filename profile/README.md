# <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/SureA11y/.github/main/profile/assets/surea11y-mark-primary.svg"><img alt="" width="46" height="46" align="absmiddle" src="https://raw.githubusercontent.com/SureA11y/.github/main/profile/assets/surea11y-mark-light-surface.svg"></picture> SureA11y

**Accessibility testing that tells you what it can't tell you.**

SureA11y is an open-source family of accessibility testing packages built around one deterministic WCAG testing engine. You run it in your own test suite, CI pipeline, or from the command line.

It automates what can be determined objectively and makes the limits of that automation explicit. Instead of hiding uncertain cases, it distinguishes between what **fails**, what **passes**, what **can't be determined automatically**, and what **doesn't apply**.

[Website & documentation](https://surea11y.dev/) · [Getting started](https://surea11y.dev/getting-started/)

## The engine

<a href="https://github.com/SureA11y/core"><picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/SureA11y/core/main/docs/assets/brand-tag-dark.svg"><img alt="surea11y core" src="https://raw.githubusercontent.com/SureA11y/core/main/docs/assets/brand-tag-light.svg"></picture></a>

[`@surea11y/core`](https://github.com/SureA11y/core) is the foundation of the ecosystem. Every other package is built on it.

- **Deterministic results.** The same input produces the same output.
- **Explicit uncertainty.** Cases that require human judgement are reported as `cantTell`, not silently ignored.
- **Conservative findings.** `fail` is reserved for objective, normative violations.
- **Standards traceability.** Rules map to the applicable WCAG Success Criterion whenever appropriate.
- **ACT validation.** Rules with a [W3C ACT](https://www.w3.org/TR/act-rules-format/) counterpart are verified against ACT's published test corpus, with a public [implementation report](https://surea11y.github.io/act-report/act-report.jsonld).
- **Stable, machine-readable output** for testing and CI workflows.
- **Zero runtime dependencies.**

> **Automate what can be determined objectively. Never pretend to automate what cannot.**

## Use it with your stack

Install the package that matches how you already test. Each one pulls in `@surea11y/core` for you and uses the same result model.

| Environment | Package |
| --- | --- |
| Playwright | [`@surea11y/playwright`](https://github.com/SureA11y/playwright) |
| Cypress | [`@surea11y/cypress`](https://github.com/SureA11y/cypress) |
| Puppeteer | [`@surea11y/puppeteer`](https://github.com/SureA11y/puppeteer) |
| Selenium | [`@surea11y/selenium`](https://github.com/SureA11y/selenium) |
| WebdriverIO | [`@surea11y/webdriverio`](https://github.com/SureA11y/webdriverio) |
| Jest / Vitest | [`@surea11y/test-matchers`](https://github.com/SureA11y/test-matchers) |
| CLI / CI | [`@surea11y/cli`](https://github.com/SureA11y/cli) |
| A DOM you already have | [`@surea11y/core`](https://github.com/SureA11y/core) |

## Four outcomes, including uncertainty

Every rule produces one of four explicit outcomes:

- `fail`: a violation provable from the DOM.
- `pass`: the rule's specific condition is met.
- `cantTell`: a human has to decide, and the result says what was ambiguous.
- `notApplicable`: the rule's precondition is not present.

A `pass` is not a claim that a page is accessible. Automated testing covers only what can be determined from the information available to the engine.

[Results and reports](https://surea11y.dev/results-reports/) · [Known limitations](https://surea11y.dev/help/known-limitations/)

## Get started

```sh
npm install @surea11y/core
```

The engine needs a DOM to read but never creates one. You supply it, whether that is jsdom, a browser automation page, or the live document. To scan static HTML without writing any code:

```sh
npx @surea11y/cli scan ./index.html
```

The [Getting Started guide](https://surea11y.dev/getting-started/) covers installation and usage for each package.

## Open source

SureA11y is an independent open-source project, developed in the open. `@surea11y/core` is licensed under MPL-2.0, and the integration packages under MIT. Every package is published on [npm](https://www.npmjs.com/org/surea11y).

Issues and contributions are welcome. See [CONTRIBUTING.md](https://github.com/SureA11y/.github/blob/main/CONTRIBUTING.md), or [core's own guide](https://github.com/SureA11y/core/blob/main/CONTRIBUTING.md) before working on a rule.

**[Explore the documentation →](https://surea11y.dev/)**
