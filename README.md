<!-- README profilu konta LunaDesktop: https://github.com/LunaDesktop
     Wrzuć jako README.md do repozytorium LunaDesktop/LunaDesktop (branch main).
     Obrazy linkują do repo `branding` i `monorepo` (gałąź main) — nie trzeba ich kopiować. -->

<p align="center">
  <img src="https://raw.githubusercontent.com/LunaDesktop/branding/main/branding/luna.svg" width="96" alt="Luna">
</p>

<h1 align="center">Luna</h1>

<p align="center">
  Mały, spójny pulpit linuksowy w czystym Rust.<br>
  <em>A small, coherent Linux desktop written in pure Rust.</em>
</p>

<p align="center">
  <img alt="Rust" src="https://img.shields.io/badge/Rust-1.80%2B-dea584?logo=rust&logoColor=white">
  <img alt="Wayland" src="https://img.shields.io/badge/Wayland-compositor-4a90d9">
  <img alt="Platform" src="https://img.shields.io/badge/platform-Linux-lightgrey">
  <img alt="License" src="https://img.shields.io/badge/license-MPL--2.0%20%2F%20GPL--3.0-blue">
  <img alt="Status" src="https://img.shields.io/badge/status-alpha-orange">
</p>

<p align="center">
  <a href="https://luna.paganlinux.eu/en/docs/">Documentation</a> ·
  <a href="https://luna.paganlinux.eu/">Website</a> ·
  <a href="https://github.com/LunaDesktop/monorepo">Monorepo</a> ·
  <a href="#polski">Polski</a>
</p>

---

<p align="center">
  <img src="https://git.paganlinux.eu/luna/raw?path=docs/images/luna-desktop.png&branch=main" width="820" alt="Pulpit Luna">
</p>

## What is Luna?

A desktop environment in the spirit of GNOME and KDE Plasma — panel, launcher, workspaces,
notifications, lock screen, login greeter, settings and everyday applications — built
bottom-up in Rust, with **no GTK, Qt, GObject or glib** anywhere in the stack.

| Layer | GNOME world | KDE world | Luna |
|---|---|---|---|
| Toolkit | GTK | Qt | **libLuna** — pure-Rust widgets |
| Desktop / shell | GNOME Shell | Plasma | **Luna** — panel, launcher, OSD, settings |
| Wayland compositor | Mutter | KWin | **Selene** — `wayland-server`, no Smithay |

Bilingual by design: every language is one `i18n/<code>.lang` file — built-in **pl**, **en**,
**de** — and new languages can be added at runtime without recompiling.

## Repositories

**Core**

| Repository | What it is |
|---|---|
| [monorepo](https://github.com/LunaDesktop/monorepo) | Working sources: Selene, luna-shell, libLuna and the apps (mirrors live in the separate repos) |
| [selene](https://github.com/LunaDesktop/selene) | Wayland compositor — DRM/KMS and nested backends, GPU `dmabuf`, XWayland with a built-in WM, IME, clipboard manager |
| [luna](https://github.com/LunaDesktop/luna) | The shell: panel, launcher, OSD, lock screen and session components |
| [libLuna](https://github.com/LunaDesktop/libLuna) | The toolkit: 77 GTK4/libadwaita-style widgets, CPU renderer, themes as design tokens |
| [luna-greeter](https://github.com/LunaDesktop/luna-greeter) | Login screen for greetd, built on libLuna |
| [branding](https://github.com/LunaDesktop/branding) | Luna-Icons theme, logos and wallpapers |

**Applications**

[files](https://github.com/LunaDesktop/files) — file manager ·
[store](https://github.com/LunaDesktop/store) — app store (pacman/pag/apt/dnf/emerge/Flatpak) ·
[settings](https://github.com/LunaDesktop/settings) — settings hub ·
[media](https://github.com/LunaDesktop/media) — audio/video player ·
[terminal](https://github.com/LunaDesktop/terminal) — PTY + VT100/xterm, no VTE ·
[clock](https://github.com/LunaDesktop/clock) — clock, timers, calendar ·
[eq](https://github.com/LunaDesktop/eq) — audio equalizer components ·
[luna-demo](https://github.com/LunaDesktop/luna-demo) — widget gallery ·
[luna-editor-ai-writer](https://github.com/LunaDesktop/luna-editor-ai-writer) — AI plugin for Luna Editor

## Quick start

```sh
git clone https://github.com/LunaDesktop/monorepo.git luna
cd luna

./scripts/workspaces.sh build    # everything (no make required)
./scripts/workspaces.sh test
./scripts/install.sh             # environment: binaries, session entry, portals
```

> Trying the compositor without logging out: `SELENE_BACKEND=nested SELENE_INPUT=none selene`.
> Without `SELENE_INPUT=none` it grabs your physical keyboard and mouse.

## Documentation

- Project site and developer docs: <https://luna.paganlinux.eu/en/docs/> (English) · <https://luna.paganlinux.eu/docs/> (polski)
- Selene protocol support (live table): [docs/compositor.md](https://github.com/LunaDesktop/monorepo/blob/main/docs/compositor.md)
- Own git mirror: <https://git.paganlinux.eu/luna.git>

## Licenses

**MPL-2.0** — libLuna, branding, monorepo. **GPL-3.0** — applications, shell and compositor.
The exact license is always in the repository's `LICENSE` file.

---

## Polski

**Luna** to środowisko pulpitu w duchu GNOME i KDE Plasma — panel, launcher, przestrzenie
robocze, powiadomienia, ekran blokady, menedżer logowania, ustawienia i aplikacje —
zbudowane od podstaw w Rust, **bez GTK, Qt, GObject i glib**.

| Warstwa | GNOME | KDE | Luna |
|---|---|---|---|
| Toolkit | GTK | Qt | **libLuna** — widgety w czystym Rust |
| Środowisko | GNOME Shell | Plasma | **Luna** — panel, launcher, OSD, ustawienia |
| Kompozytor Wayland | Mutter | KWin | **Selene** — `wayland-server`, bez Smithery |

**Repozytoria**

- rdzeń: [monorepo](https://github.com/LunaDesktop/monorepo) (źródła robocze),
  [selene](https://github.com/LunaDesktop/selene) (kompozytor),
  [luna](https://github.com/LunaDesktop/luna) (powłoka),
  [libLuna](https://github.com/LunaDesktop/libLuna) (toolkit),
  [luna-greeter](https://github.com/LunaDesktop/luna-greeter) (logowanie),
  [branding](https://github.com/LunaDesktop/branding) (ikony, logo, tapety)
- aplikacje: [files](https://github.com/LunaDesktop/files),
  [store](https://github.com/LunaDesktop/store),
  [settings](https://github.com/LunaDesktop/settings),
  [media](https://github.com/LunaDesktop/media),
  [terminal](https://github.com/LunaDesktop/terminal),
  [clock](https://github.com/LunaDesktop/clock),
  [eq](https://github.com/LunaDesktop/eq),
  [luna-demo](https://github.com/LunaDesktop/luna-demo),
  [luna-editor-ai-writer](https://github.com/LunaDesktop/luna-editor-ai-writer)

**Szybki start**

```sh
git clone https://github.com/LunaDesktop/monorepo.git luna
cd luna
./scripts/workspaces.sh build
./scripts/workspaces.sh test
./scripts/install.sh
```

Kompozytor można uruchomić zagnieżdżony w innej sesji:
`SELENE_BACKEND=nested SELENE_INPUT=none selene` — bez `SELENE_INPUT=none` przejmie Twoją
klawiaturę i mysz.

**Dokumentacja:** <https://luna.paganlinux.eu/docs/> (polski) i
<https://luna.paganlinux.eu/en/docs/> (English). Wsparcie protokołów kompozytora:
[docs/compositor.md](https://github.com/LunaDesktop/monorepo/blob/main/docs/compositor.md).

**Licencje:** MPL-2.0 (libLuna, branding, monorepo) i GPL-3.0 (aplikacje, powłoka, kompozytor).
