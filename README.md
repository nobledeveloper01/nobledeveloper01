# Marvellous Bamisaye

**Full-stack engineer.** I build the parts of a product people see — interfaces,
flows, dashboards — and the parts they should never have to think about: payment
infrastructure, reconciliation, compliance.

Frontend in React and TypeScript. Mobile in React Native and Flutter, down to
Kotlin and Swift where the platform makes you — and native Swift outright when
the platform is the point. Backends in Go, C#, Python and Node. Postgres
underneath.

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

Eight products for the Nigerian market, none of them fintech. Six are
cross-platform from one codebase, with functional parity as a hard requirement
rather than an aspiration — all six are under way. **Two are native iOS, by decision**, each with the case for
going native written down before the code; both are built as far as a simulator
reaches.

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

### [Vitals](https://github.com/nobledeveloper01/vitals) — the previous page, wherever the patient is
A Nigerian primary health record is a paper card, and the card stays where it
was written. The hard problem is not the record; it is **merging two records
that were both edited while neither could see the other** — two nurses on two
tablets, offline for a week, both updating the same child. A last-writer-wins
system silently destroys clinical data there, and here silent data loss is
not a bug, it is a patient harm. Vitals treats observations as immutable facts
that merge by union, never by overwrite; five merge invariants are
property-tested over generated multi-device worlds, and the .NET replica runs
the same merge in C#, held to the Dart by a 200-world parity fixture that
caught the first real defect the same night.

**Nothing clinical is computed.** A pulse is shown beside the published range
and marked *outside range* by a comparison, never named. The antenatal danger
signs are ten questions a nurse answers, each one, and nothing sums them — a
test greps the domain for *score*, *risk*, *triage* so a future one fails
before it is a regulated device. A pack is *on the list*, *not on the list*, or
*the list cannot say*, and no language it speaks has the fourth word. The
patient hands the record over on an animated QR built from a grant they chose
— which sections, to whom, until when — and a fact outside the grant is never
in the bytes. Every open of a record is a fact the patient sees on their own
phone.

`Dart` `Flutter` `C#/.NET 9` `Postgres` `ChaCha20-Poly1305` `Ed25519` — glass
over a gradient mesh with a solid twin for a three-year-old tablet; five
patient-face languages held complete by a gate; a domain that imports nothing;
nine build gates, each broken on purpose and watched to fire; a signed audit
export a supervisor verifies with nothing but Python. Built in one night to the
edge of its hardware gates: mixed Android↔iOS transfer, the reference tablet,
and a clinician reading every screen.

### [Sentinel](https://github.com/nobledeveloper01/sentinel) — your circle, told; nobody else
Community safety and emergency alerting, and the only product in this
portfolio where a design error causes direct physical harm: a false alarm can
start a mob, and a "suspicious person" report can get somebody killed. So the
rules were written before the code, and they are the product. **Alerting your
own circle is a right; alarming strangers is a privilege.** The personal path
— the panic action, the safe-arrival journey that escalates even if the phone
dies — is fast and unmetered because it reaches people who already trust you.
The public path is earned: a report is visible to 500 m and widens only with
independent corroboration, computed by a pure function that is property-tested
over generated worlds so that **no single account, and no set of accounts
sharing an independence signal, can carry an unverified report beyond 500 m.**

Nothing about a person, ever — no names, no photographs, no plates, no
*suspicious person* category, and a free-text screen that fails closed. No
engagement — no counts, no badges, no analytics SDK. The server cannot read a
location: alert and journey positions leave the phone sealed to the circle's
keys, and a test hands the server everything it holds and proves it cannot
open one. There is no red in the palette and no `danger` token, because a
safety app that shouts manufactures fear.

`TypeScript` `React Native` `C#/.NET 9` `Postgres` `X25519` `XChaCha20-Poly1305`
— a domain that imports nothing, a C# replica held to it by a 200-world
fixture, a copy gate that bans the words that would cross the line, and eight
gates each broken on purpose and watched to fire. Started the same day as
Vitals; what it waits on is a handset with a stopwatch, an outside reading of
the abuse model, and thirty days in one city with zero harm.

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

### [Tender](https://github.com/nobledeveloper01/tender) — which note is this?
Naira notes have no tactile marking. A blind Nigerian handling cash is trusting
the other party, every time — and since the 2022 redesign there are eleven
visually distinct notes carrying eight values. Every currency reader on the
market covers the dollar, euro, pound, rupee and yen. None covers the naira.

Tender is native Swift and iOS only, and the reason is written down before the
code: its user never looks at the screen, so the accessibility layer is not a
feature of the interface — it *is* the interface — and that layer is the
platform's own. Point the camera; the app says which note, through VoiceOver,
and pulses it through the haptic engine in a pattern different for every value,
so the answer lands in a market too loud to hear a phone. It names the
denomination and **never whether the note is genuine**; a word-list gate keeps
that sentence out of the app, permanently.

`Swift 6` `SwiftUI` `Core ML` `Core Haptics` `AVFoundation` — a domain package
that imports nothing, not even Foundation; Xcode's accessibility audit on every
screen at two text sizes; twelve build gates, each broken on purpose and watched
to fire. No backend, and a gate that fails on any network path in the source.

It stops at a different wall from the other two, and a better one: a week of
photographing eleven banknotes, which is the one gate in this portfolio that
waits on nobody but me.

### [Snag](https://github.com/nobledeveloper01/snag) — the flat, on the day it can still be written down
A Lagos tenant pays two years' rent in advance plus a caution fee, and two years
later argues about a cracked tile that was cracked on move-in day — with nothing
to argue it with. Snag is the record made on the day it can still be made
honestly: walk the flat room by room, photograph what is wrong and what is fine,
seal it. **The evidence is the wedge, not the dispute.** The report is worth
making for one tenant with no landlord on the other side.

Every photograph is hashed the moment it is taken and stripped of everything but
the picture. The report is sealed with a key that never leaves the phone — the
Secure Enclave where there is one — and the sealed bundle carries the public
key, so any phone with Snag, or a 200-line Python script written from the format
document alone, says *unaltered since signing* or *altered*, and nothing in
between. The landlord counter-signs on the tenant's phone; a move-out walk shows
the move-in photograph beside the shutter and says what changed; a scan added
months later is a second signature beside the first, touching nothing the first
one signed. It says **evidence, never proof**, on its own last page, and a
word-list gate keeps the stronger word out of every language it speaks — five
of them, chosen in the app.

`Swift 6` `SwiftUI` `CryptoKit` `ARKit` `RoomPlan` `ActivityKit` — a domain
package that imports nothing, a canonical byte encoding asserted by a checked-in
fixture, a verifier proved against every flipped byte of every file, and two
verifiers that must agree. Ten build gates, each broken on purpose and watched
to fire. No backend,
by decision, and nothing sent — the one exception, the tenant's own iCloud, is
opt-in and named in an ADR.

What it waits on is a phone in a hand: the measured tier is ARKit and the
scanned tier is LiDAR, both built and proved with a fixture room where the
simulator has no sensor, and a tape measure in a real room is the gate.

The cross-platform six stop at the same wall, and it is the honest one: a **device day** on a
Transsion handset whose power management is undocumented, and a **native
speaker** for the Hausa, Yorùbá and Igbo. Roughly 2,500 translated keys between
them, written by somebody who speaks none of the three. Automated checks prove
every string on every screen goes through the table; nothing proves one is right.
Both projects list that as a release blocker rather than a nice-to-have.

Every one of the eight is documented the same way — the problem, how it works,
each layer, the correctness notes, what is open and why — so a reader who has
read one knows where to look in the next.

[Where each one stops, and why →](https://github.com/nobledeveloper01/backhaul#11-status)

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

**Mobile** · React Native · Flutter · Swift / SwiftUI · Kotlin

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
