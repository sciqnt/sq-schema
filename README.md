# sq-schema · `sciqnt-schema`

sq-schema — the canonical cross-asset contract for sciqnt (point-in-time-correct schema + conformance + JSON-Schema artifact).

> **Published from the monorepo.** During the component-world transition this repo
> is *generated* from [`sciqnt/sciqnt`](https://github.com/sciqnt/sciqnt)
> (`core/sq_schema`) by its publishing bot. The monorepo is the source of truth
> until the contract has fully graduated; **edit there**, not here. Role: `contract-hub`.

## Install

```bash
pip install sciqnt-schema
```

## What it is

The thin, stable **contract** every sciqnt connector translates *into* and every
consumer reads *from* — never broker JSON. Money is `Decimal`; every fact is
bitemporal (`valid_at` + `observed_at`). This package computes no P/L — adapters
fill the fields, consumers read them.

The contract is also published as a **language-agnostic JSON-Schema artifact**,
[`contract.schema.json`](src/sq_schema/contract.schema.json), so a connector in
any language — or a reviewing agent — can read and diff it. Regenerate it from the
models with `python -m sq_schema.json_schema --write`; CI fails if it drifts.

## Governance

Inherits the org's reusable workflows (CI, principle-review, @claude, issue-triage)
from [`sciqnt/sq-constitution`](https://github.com/sciqnt/sq-constitution). Licensed
MIT; contributions are DCO sign-off, never a CLA.
