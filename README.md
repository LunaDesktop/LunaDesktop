<!-- Szablon README PROFILU GitHub (repo <login>/<login>, plik README.md).
     Podmień: @mijsys na swój login, adresy repo i linki kontaktowe. -->

<p align="center">
  <a href="https://github.com/LunaDesktop/monorepo"><img alt="Luna" src="https://img.shields.io/badge/-Luna-1f2430?style=flat-square&labelColor=1f2430"></a>
  <a href="https://github.com/LunaDesktop/selene"><img alt="Selene" src="https://img.shields.io/badge/-Selene-4a90d9?style=flat-square"></a>
  <a href="https://github.com/mijsys/libLuna"><img alt="libLuna" src="https://img.shields.io/badge/-libLuna-dea584?style=flat-square"></a>
</p>

<h1 align="center">Patryk</h1>

<p align="center">
  Buduję <b>Lunę</b> — mały, spójny pulpit linuksowy w czystym Rust.<br>
  <em>I build Luna — a small, coherent Linux desktop in pure Rust.</em>
</p>

<p align="center">
  <img alt="Rust" src="https://img.shields.io/badge/Rust-1.80%2B-dea584?logo=rust&logoColor=white">
  <img alt="Wayland" src="https://img.shields.io/badge/Wayland-compositor-4a90d9">
  <img alt="Linux" src="https://img.shields.io/badge/platform-Linux-lightgrey">
  <img alt="License" src="https://img.shields.io/badge/license-MPL--2.0-blue">
</p>

---

## Co buduję / What I'm building

Trzy warstwy jednego stosu — bez GTK, Qt, GObject i glib. Każda jest osobnym
workspace'em Cargo, więc można ją wydać i rozwijać niezależnie.

| Projekt | Co to jest | Stan |
|---|---|---|
| **[Luna](https://github.com/LunaDesktop/monorepo)** | Środowisko pulpitu: panel, launcher, przestrzenie robocze, powiadomienia, ekran blokady, menedżer logowania, ustawienia i aplikacje (Pliki, Edytor, Media, Zegar, Sklep, Terminal) | alpha |
| **[Selene](https://github.com/LunaDesktop/selene)** | Kompozytor Wayland — bez Smithery: `wayland-server` i własna pętla zdarzeń. Backendy DRM/KMS i nested, import GPU `dmabuf`, XWayland z wbudowanym WM i mostem schowka, IME, menedżer schowka | alpha |
| **[libLuna](https://github.com/mijsys/libLuna)** | Toolkit GUI w czystym Rust — 77 widgetów wzorowanych na GTK4/libadwaita, renderer CPU (tiny-skia), motywy jako tokeny | 0.0.8 |

**Dlaczego od zera:** bo „mały, szybki i bezpieczny pamięciowo” da się osiągnąć tylko wtedy,
gdy cały stos jest w jednym języku i pod naszą kontrolą — od geometrii, przez widgety, po
kompozytor. Integracja ze światem zewnętrznym idzie standardowym Waylandem
(`xdg-shell`, `wlr-layer-shell`), portalami XDG i XWaylandem.

## Na czym teraz pracuję / Current focus

- kompozytor: `xdg_toplevel` v2+ (`wm_capabilities`, `configure_bounds`, stan kafelkowania)
- pełne HiDPI (`buffer_scale`/`buffer_transform`, skalowanie ułamkowe)
- `ext_session_lock_v1` i screencopy dla narzędzi trzecich
- schowek poza tekstem: obrazy, HTML, `text/uri-list`, `PRIMARY`
- codzienna praca bez obejść: XWayland, gry, IME

## Stos / Stack

`Rust` · `Wayland` (`wayland-server`, `wayland-client`) · `DRM/KMS` · `EGL`/`dmabuf` ·
`tiny-skia` · XKB · `wlr-*` protocols · `systemd`/`greetd` · Linux

## Projekty wokół Luny

- **Dokumentacja:** <https://luna.paganlinux.eu/docs/> (polski) · <https://luna.paganlinux.eu/en/docs/> (English)
- **Wsparcie protokołów Selene:** [docs/compositor.md](https://github.com/LunaDesktop/selene/blob/main/docs/compositor.md)
- **Dystrybucja / pakiety:** PaganOS — receptury w `packaging/paganos`
- **Własne repozytorium git:** <https://git.paganlinux.eu/luna.git>

## Zasady, w których pracuję

- **Rust 2021, MSRV 1.80** — bez ciężkich zależności bez powodu.
- **Komentarz mówi „dlaczego”, nie „co”**; testy jednostkowe w `mod tests`.
- **Zero obietnic bez pokrycia** — dokumentacja protokołów jest żywą listą tego, co działa,
  i tego, czego jeszcze nie ma.
- **Najpierw reprodukcja, potem poprawka** — test w zagnieżdżonej sesji zamiast zgadywania.

## Kontakt / Contact

<p align="left">
  <a href="https://luna.paganlinux.eu/">Strona projektu</a> ·
  <a href="https://github.com/LunaDesktop">GitHub</a> ·
  <a href="https://git.paganlinux.eu/luna.git">Repozytorium</a>
</p>

<sub>Otwarty na zgłoszenia i pull requesty. Issues z reprodukcją w zagnieżdżonej sesji
Selene (`SELENE_BACKEND=nested SELENE_INPUT=none`) rozwiązywane są najszybciej.</sub>

<!--
  Opcjonalnie: karta statystyk GitHuba (usługa zewnętrzna github-readme-stats,
  renderuje obrazek z publicznych danych — usuń, jeśli nie chcesz zewnętrznych odwołań).

<p align="center">
  <img height="150" src="https://github-readme-stats.vercel.app/api?username=mijsys&show_icons=true&hide_title=true&theme=transparent" alt="">
  <img height="150" src="https://github-readme-stats.vercel.app/api/top-langs/?username=mijsys&layout=compact&theme=transparent" alt="">
</p>
-->
