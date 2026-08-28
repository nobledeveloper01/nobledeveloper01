# Marvellous Bamisaye

**Full-stack engineer.** I build the parts of a product people see — interfaces,
flows, dashboards — and the parts they should never have to think about: payment
infrastructure, reconciliation, compliance.

Frontend in React and TypeScript. Mobile in React Native and Flutter, down to
Kotlin and Swift where the platform makes you. Backends in Go, C#, Python and
Node. Postgres underneath.

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

## Mobile, and a different kind of hard

Six products for the Nigerian market, none of them fintech. **Two are built**;
the other four are specified to the same depth. Cross-platform from one codebase
in every case, with functional parity as a hard requirement rather than an
aspiration.

### [Backhaul](https://github.com/nobledeveloper01/backhaul) — the truck, followed from wherever the load was agreed
Almost every load in Nigerian road freight is agreed on WhatsApp. Backhaul does
not try to replace that — it lets a shipper type the two phone numbers they have
been messaging and track the truck from there. **Tracking is the wedge; matching
is the business**, and the marketplace is worth nothing until the tracking has
earned somebody's trust.

The engineering is in the parts that must not stop: a native capture loop that
keeps recording when the network goes, because stopping loses precisely the
stretch of road nobody can account for afterwards; a delivery a driver can
photograph, sign and seal at a market gate **with no signal at all**, because the
alternative is a driver who finished the run and is not paid. Nothing that is an
estimate is ever rendered as a measurement — the arrival window refuses outright
rather than guessing, and says what would fix it.

`TypeScript` `React Native` `Kotlin` `Swift` `C#/.NET 9` `Postgres` — one domain
package, four faces, and a parity suite holding the C# server to it.

### [Grid](https://github.com/nobledeveloper01/grid) — the electricity bill you can actually dispute
A Nigerian household disputing a bill has nothing to dispute it with: no reading
history, no record of how long the power was actually on, no document anyone is
obliged to read. Grid records both, values the gap between the service band you
pay for and the hours you got, and assembles it into a pack a distribution
company and a regulator will accept.

**No backend at all in v1.** Everything a household needs to act — OCR, supply
inference, the arithmetic, the PDF — runs on the phone, because the people who
need it most are the ones whose data ran out.

`Dart` `Flutter` `Kotlin` `Swift` `Go` `Postgres` `SQLite/Drift`

Both stop at the same wall, and it is the honest one: a **device day** on a
Transsion handset whose power management is undocumented, and a **native
speaker** for the Hausa, Yorùbá and Igbo. Roughly 2,500 translated keys between
them, written by somebody who speaks none of the three. Automated checks prove
every string on every screen goes through the table; nothing proves one is right.
Both projects list that as a release blocker rather than a nice-to-have.

[All six, and why each stops where it does →](https://github.com/nobledeveloper01/backhaul#11-what-is-not-done-and-why)

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

**Languages** · TypeScript · JavaScript · Go · C# · Python · Dart · Kotlin · Swift · SQL

**Frontend** · React · Next.js · Vue · Tailwind

**Mobile** · React Native · Flutter · Kotlin · Swift

**Backend** · .NET · Go · Django · Node / Express

**Data** · Postgres · SQL Server · MongoDB · Redis

**Infrastructure** · Docker · Kubernetes · Helm · Terraform · GitHub Actions

**Certified** · ISO/IEC 27001:2022 — Information Security Management Systems (ISMS) Foundation ([SandBP](https://sandbp.net), Aug 2026)

---

## How I like to work

I write things down before I build them. Every project above carries a set of
architecture decision records explaining not just what was chosen but what was
rejected and why — because the reasoning is the part that's expensive to
reconstruct, and the part that's gone once the person who had it leaves.

I also try to make the failure modes explicit. A system that says `unknown` when it
doesn't know is more useful than one that guesses confidently, and most of the
interesting work is in deciding what a service will refuse to do.

The same applies to what *isn't* finished. Each project's README says where it
stopped and what would actually close it — a handset, a translator, a developer
account — rather than leaving a reader to guess whether something was hard or
just never got done. A blocker that needs a person is not the same as a blocker
that needs an afternoon, and writing that down is cheaper than the conversation
it saves.

That is also why the ISO 27001 work matters to me rather than sitting on a shelf. The
standard is largely about being able to *show* what happened — access control, audit
logging, data classification, evidence retention — which is the same problem the
hash-chained audit trails and row-level tenant isolation in these projects exist to
solve.

---

*Open to backend and full-stack work — and always happy to talk about fintech
infrastructure.*
