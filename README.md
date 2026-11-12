**English** | [Русский](README.ru.md)

# dfcl — Darwin/FreeBSD Compatibility Layer

Run a selected subset of Darwin/macOS Mach-O applications — and
PlayStation 4/5 (Orbis ELF) homebrew guests — on FreeBSD. No Linux
intermediary, no macOS VM, no CPU emulation: guest code executes on
the physical CPU of the FreeBSD host.

**Distribution model (early stage):** demo videos, compiled binaries
and test-run evidence are public; the source code and internal
engineering documentation are not published at this stage. Every
public claim below is backed by a reproducible demo or an archived
test run — not by promises.

## Proven by demos and archived test runs

| Capability | Evidence |
|---|---|
| **FreeBSD kernel module** (`compat_darwin.ko`) | compiled and loaded on FreeBSD 14.x; kernel log records the Mach-O activation path ([demo video](docs/demo/darwin_m2_exec_demo.mp4)) |
| **Native Mach-O execution** | a static x86_64 Mach-O binary executes on FreeBSD and exits 0 — via the kernel imgact, no emulation ([result screenshot](docs/demo/darwin_m2_result.png)) |
| **Orbis (PS4) ELF execution** | `orbisrun --exec` runs a PS4 homebrew ELF; guest `write()` prints "dfcl orbis ok", exit 0 on FreeBSD 14.5 ([demo video](docs/demo/o1exec_demo.mp4)) |
| **Orbis (PS5) ELF execution** | PS5 guest ELF (abiversion 2, base 0x200000000) executes natively on the same host ([demo video](docs/demo/ps5_exec_demo.mp4)) |
| **Orbis retail-asset boot research** | a PS4 title boots to its asset-loading stage with real (user-supplied) game assets on FreeBSD — no game or Sony assets are distributed ([demo video](docs/demo/deadcells_freebsd_loading_assets.mp4)) |
| **Automated test suite** | 1,677 checks, 0 failures, ASan/UBSan clean — archived per run with the tree commit id |
| **Orbis HLE libkernel** | 377-entry NID registry, 15 native passthrough shims (open/read/write/close/…), end-to-end file cycle tested |

Demo folder: [docs/demo/](docs/demo/) — videos, screenshots and the
SSH session log of the recorded runs.

## What does NOT work yet (honestly)

- Mach-O execution beyond static POSIX binaries: dyld, libSystem,
  Objective-C, graphics (Metal/CoreGraphics), XPC/launchd.
- Orbis: full game-level compatibility — GPU (GNM→Vulkan translation
  is a years-scale effort), audio, controllers are separate stages.
- Fat/universal binaries, arm64e/PAC — safe rejection, not a crash.

The roadmap fixes the order of work, not a schedule. No dates promised.

## Downloads (compiled binaries)

Prebuilt tools are attached to [Releases](../../releases):
`dfexec` (Mach-O loader/launcher), `dfinspect` (Mach-O diagnostics),
`orbisrun` (Orbis ELF launcher). Built on FreeBSD/amd64.

*Binaries are provided for evaluation of the demonstrated capabilities.
The FreeBSD kernel module (`compat_darwin.ko`) is not distributed at
this stage — its build requires a matching FreeBSD kernel source tree;
a demonstration setup is available to partners on request.*

## Supporting the project

Development runs on a single machine today; funding goes to dedicated
test hardware (bare-metal FreeBSD host, PS5, Apple Silicon, AMD
APU-class machines) and continuous test infrastructure. Goals are
tracked, cheapest first, with a public ledger in [SPONSORS.md](SPONSORS.md).

- **Boosty** (RU cards, subscriptions): https://boosty.to/bsdnrg
- **Crypto** (TON / USDT-TON / BTC): see [SPONSORS.md](SPONSORS.md)

## Legal notice

macOS, Mac, PlayStation, PS4 and PS5 are trademarks of their
respective owners. dfcl is an independent project: it distributes no
Apple or Sony assets, firmware, keys or proprietary libraries —
users provide their own legally obtained software. All engineering is
clean-room, based on public file-format documentation.

## License

Distributed materials (documentation, test evidence, binaries) —
BSD-2-Clause (see [LICENSE](LICENSE)). Source availability is
announced separately.
