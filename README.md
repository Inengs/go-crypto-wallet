# Crypto Wallet & Ledger Service

A small, production-style crypto wallet and ledger service built in Go — the proof-of-work project for the crypto vertical of my backend job search (payments, IoT, crypto, metering).

## Why this project exists

Most "wallet" tutorials fake the hard part. This one is meant to actually wrestle with:

- **Double-entry ledger integrity** — every balance change is two entries (debit + credit), never a single mutated number.
- **Concurrency safety** — no lost updates or double-spends under concurrent requests.
- **Idempotency** — the same transaction request submitted twice must never be applied twice.
- **Auditability** — every balance is derivable from its transaction history, not just stored and trusted.

## Planned scope

- [ ] Account creation + balance queries
- [ ] Double-entry transaction model (debit/credit pairs, never a raw balance update)
- [ ] Idempotent transaction submission (idempotency keys)
- [ ] Concurrency-safe transfers (row-level locking or optimistic concurrency)
- [ ] Full transaction history / audit log per account
- [ ] REST API (Go, `net/http` or a minimal router)
- [ ] PostgreSQL for storage
- [ ] Tests that actually prove the guarantees above — concurrent transfer tests, idempotency-replay tests, not just happy-path tests

## Stack

- Go
- PostgreSQL

## Status

🚧 Early stage — this repo currently holds the plan. Clone it locally to start building.

## Getting started

```bash
git clone <this-repo-url>
cd <repo-name>
go mod tidy
```
