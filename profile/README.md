<p align="center">
  <picture>
    <source srcset="https://www.emibsd.org/assets/img/ferffy-lines-white.svg" media="(prefers-color-scheme: dark)">
    <img src="https://www.emibsd.org/assets/img/ferffy-lines-black.svg" alt="Ferffy, the EmiBSD mascot: a spiky crab, drawn in line art" width="150">
  </picture>
</p>

# EmiBSD

**A port of the OpenBSD -current kernel to Rust.** An operating system in Rust, grown from the
faithful port of the OpenBSD kernel: the same system-call ABI, so OpenBSD's own userland runs
on it unmodified, and inside, a kernel rebuilt subsystem by subsystem with zero `unsafe` as the
goal.

> **Pre-alpha.** EmiBSD boots only in QEMU, on arm64. Its crypto, network and storage code is
> unaudited. Do not use it for anything real.

## Repositories

| Repository | What it is |
|---|---|
| [**LandingZone**](https://github.com/EmiBSD/LandingZone) | The OpenBSD kernel ported to Rust one C file at a time, keeping the C's shape so every file can be checked against its origin. Fidelity first. |
| [**Kernel**](https://github.com/EmiBSD/Kernel) | The redesign: what LandingZone ported, rebuilt with Rust's ownership in place of C's conventions. Crates `kernel` and `abi` are `#![forbid(unsafe_code)]`; only `hal` may hold `unsafe`, each site with a written proof. |
| [**Userland**](https://github.com/EmiBSD/Userland) | The base system above the kernel: one tree where every program, library and configuration file sits by what it does, not by where history left it. Its shape is settled; its content is at the start. |
| [**DevTools**](https://github.com/EmiBSD/DevTools) | The toolchains, imported and built once: LLVM as OpenBSD ships it for the C, and a pinned stable Rust with its `std` for `aarch64-unknown-openbsd`, released as artifacts the other repositories consume. |
| [**Portal**](https://github.com/EmiBSD/Portal) | The website, [www.emibsd.org](https://www.emibsd.org). |

The forks in this organisation (`OpenBSD-src`, `rust`, `llvm-project`, `cargo`) are read-only
mirrors of the sources the repositories pin; nothing of ours is committed to them.

## Where it stands

Milestones N0 to N4 (bootstrap, leaves, foundations, memory, processes) are met; N5, the VFS and
the file systems, is under way. The [Status](https://www.emibsd.org/status/) page has every milestone, the slices of the latest
one, and the `unsafe` count of each crate, at a named commit.

## How it is built

The work is carried out by AI coding agents under fixed roles and written rules; one maintainer
takes the decisions and approves every commit. The [Process](https://www.emibsd.org/process/)
page explains the pipeline from the 1:1 port to the redesign.

## Links

[Website](https://www.emibsd.org) ·
[About](https://www.emibsd.org/about/) ·
[Contributing](https://www.emibsd.org/contributing/) ·
[Support the project](https://www.emibsd.org/support/) ·
[News feed](https://www.emibsd.org/news/feed.xml)

EmiBSD is an independent experiment built on OpenBSD's source code. It is not affiliated with or
endorsed by the [OpenBSD](https://www.openbsd.org/) project. New code is ISC; files derived from
OpenBSD keep their original licence notices, whole.
