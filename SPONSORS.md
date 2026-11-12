# Supporting dfcl

dfcl is an independent research project: a FreeBSD-based OS layer that
loads and runs Darwin/macOS (Mach-O) and PlayStation 4/5 (Orbis ELF)
software natively — no CPU emulation, no Linux intermediary, no macOS VM.
One OS base, two compatibility targets.

Development is test-driven: every public claim is backed by a
reproducible demo or an archived test run (currently **1,698** checks
green, ASan/UBSan clean). Donations go to dedicated test hardware and
continuous test infrastructure; every purchase is reported publicly in
the ledger below.

> GitHub Sponsors is unavailable in the maintainer's region, so funding
> runs through the external channels below.

## Ways to contribute

| Channel | Best for | Where |
|---|---|---|
| Boosty | Russian cards, subscriptions | `https://boosty.to/bsdnrg` |
| TON | Global, near-zero fees | `EQ…` *(address pending)* |
| USDT (TON) | Global, stable value | `EQ…` *(address pending)* |
| BTC | Global | `bc1…` *(address pending)* |

## Hardware goals (cheapest first, unlocked one by one)

| # | Goal | Unlocks | Est. cost | Status |
|---|---|---|---|---|
| 1 | FreeBSD dev host (bare-metal mini-PC) | bhyve CI for the kernel module; driver bring-up; no VM quirks | ~$400 | ⬜ 0 % |
| 2 | PlayStation 5 (used) | Orbis syscall-table verification; homebrew ELF test targets | ~$600 | ⬜ 0 % |
| 3 | Apple MacBook Pro (M5) | Apple Silicon / Darwin arm64 validation on real hardware | ~$2,500 | ⬜ 0 % |
| 4 | AMD MI300A node | Heterogeneous-compute (APU) research | ~$30,000 | 🔒 long-term |

**Note:** the current milestones do **not** require donations — demos run
in a FreeBSD VM. Funding accelerates what follows, it does not gate it.

## Other ways to help

- **Donate hardware** — ship a device (write first: shipping constraints apply)
- **Donate access** — SSH to your PS5 / Mac / AMD box for test runs
- **Spread the word** — Show HN, r/freebsd, r/ps4homebrew, Phoronix tips

## Ledger

Every donation and purchase is recorded here.

| Date | Channel | Amount | Purpose |
|---|---|---|---|
| — | — | — | — |

## Legal note

No Apple or Sony assets are distributed: no firmware, no keys, no
proprietary libraries, no game dumps. Guests must be legally obtained
by the user; demo videos show user-provided, legally obtained software.
