# Marvellous Bamisaye

**Full-stack engineer.** I build the parts of a product people see — interfaces,
flows, dashboards — and the parts they should never have to think about: payment
infrastructure, reconciliation, compliance.

Frontend in React and TypeScript. Backends in Go, C# and Python. Postgres underneath.

[**Portfolio**](https://marvellous-bamisaye.vercel.app) · [LinkedIn](https://www.linkedin.com/in/marvellous-bamisaye-b7858524a) · [Twitter](https://twitter.com/MarvellousJosh2) · <nobleconcepts22@gmail.com>

---

## What I'm building

Four services a fintech needs at the edges of its ledger. Each does one job and
refuses to do the rest — **none of them can move money, by construction.**

### [StatusHub](https://github.com/nobledeveloper01/StatusHub) — one receiver in front of every payment provider
Verifies each provider's signature, normalises every payload into one canonical
schema, and forwards with ordering, retries and replay. Raw bytes hit Postgres
*before* anything tries to parse them, so a payload we can't understand is still a
payload we didn't lose. An unrecognised status becomes `unknown` — never a guess.

`Go` `Postgres` `TypeScript` · [statushub site →](https://nobledeveloper01.github.io/StatusHub/)

### [ReconSync](https://github.com/nobledeveloper01/ReconSync) — finds the debits whose credit never arrived
The system that failed cannot be the system that detects the failure. ReconSync
watches both legs of a transfer and fires a signed **advisory** reversal webhook
before the regulatory window closes. It checks its own blind spots first: if its
ingest had a gap, a missing credit proves nothing.

`Go` `Postgres` `TypeScript` · [reconsync site →](https://nobledeveloper01.github.io/ReconSync/)

### [ComplyLayer](https://github.com/nobledeveloper01/ComplyLayer) — allow, flag or block in under 100ms
Compliance rules written, tested and approved by the compliance officer — no
engineer, no pull request, no deploy. Every verdict cites the regulation it
implements and carries a message a customer can actually read. Division isn't in the
rule grammar: a decision made six months ago has to reproduce exactly.

`Python` `Django` `Postgres` · [complylayer site →](https://nobledeveloper01.github.io/ComplyLayer/)


### [DisputeShield](https://github.com/nobledeveloper01/DisputeShield) — a script tag, and the clock starts
A dispute-filing interface for your customers and an SLA-tracked, immutably audited
case system for compliance — without building a ticketing product. The clock cannot
be paused, because a pausable clock is an abusable one; the alert fires *before* the
breach, not after; and there is no code path to a payment, enforced by a call-graph
test rather than by convention.

`Python` `Django` `Postgres` `Redis` · [disputeshield site →](https://nobledeveloper01.github.io/DisputeShield/)

---

## What I work on professionally

| Domain | What that looked like |
| --- | --- |
| **Insurance & brokerage** | Customer and broker web apps, and the .NET APIs behind them |
| **Payments & revenue assurance** | Collection, reconciliation and reporting for public-sector revenue |
| **Edtech** | Reader, creator and admin dashboards, plus a mobile app |
| **Property & rentals** | Listing and application flows, React front to .NET back |

Contract and in-house, across Nigerian and US teams.

---

## Tech

**Languages** · TypeScript · JavaScript · Go · C# · Python · SQL

**Frontend** · React · Next.js · Vue · Tailwind · React Native

**Backend** · .NET · Go · Django · Node / Express

**Data** · Postgres · SQL Server · MongoDB · Redis

**Infrastructure** · Docker · Kubernetes · Helm · Terraform · GitHub Actions

---

## How I like to work

I write things down before I build them. The three projects above each carry a set of
architecture decision records explaining not just what was chosen but what was
rejected and why — because the reasoning is the part that's expensive to
reconstruct, and the part that's gone once the person who had it leaves.

I also try to make the failure modes explicit. A system that says `unknown` when it
doesn't know is more useful than one that guesses confidently, and most of the
interesting work is in deciding what a service will refuse to do.

---

*Open to backend and full-stack work — and always happy to talk about fintech
infrastructure.*
