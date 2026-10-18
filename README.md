<a id="top"></a>

<div align="center">

[![Deutsch](https://img.shields.io/badge/🇩🇪_Deutsch-24292f?style=for-the-badge)](#deutsch)
[![English](https://img.shields.io/badge/🇬🇧_English-24292f?style=for-the-badge)](#english)

</div>

---

<a id="deutsch"></a>

<div align="center">

# ESP32 Marauder – Waveshare ESP32-C5

Mein eigenes vollständiges Waveshare-Paket für das 3,5-Zoll-Touchdisplay,
veröffentlicht auf dem Standardbranch `master` dieses Forks.

`ESP32-C5` · `C++` · `Arduino` · `PowerShell` · `3D-Druck`

</div>

<div align="center">

[![Paket öffnen](https://img.shields.io/badge/Paket_%C3%B6ffnen-24292f?style=for-the-badge)](contrib/waveshare-esp32-c5-35/README.md)
[![Übersicht](https://img.shields.io/badge/%C3%9Cbersicht-24292f?style=for-the-badge)](#de-uebersicht)
[![Paketinhalt](https://img.shields.io/badge/Paketinhalt-24292f?style=for-the-badge)](#de-paketinhalt)
[![Hardware](https://img.shields.io/badge/Hardware-24292f?style=for-the-badge)](#de-hardware)
[![Build und Flashen](https://img.shields.io/badge/Build_und_Flashen-24292f?style=for-the-badge)](#de-build)
[![Validierung](https://img.shields.io/badge/Validierung-24292f?style=for-the-badge)](#de-validierung)
[![Lizenz](https://img.shields.io/badge/Lizenz-24292f?style=for-the-badge)](#de-lizenz)

</div>

---

<a id="de-uebersicht"></a>

## Übersicht

Das Paket bündelt die Firmware, den vollständigen Quell-Snapshot, das
Board-Profil, Build- und Flash-Hilfsskripte, den Verdrahtungsplan sowie
druckbare Gehäuseteile für meinen Waveshare-Aufbau.

Die [Paket-README](contrib/waveshare-esp32-c5-35/README.md) ist der Einstieg
für Einrichtung und Nutzung. Die verlinkte technische Detaildokumentation
liegt derzeit auf Englisch vor.

<a id="de-paketinhalt"></a>

## Paketinhalt

| Bereich | Inhalt | Direktlink |
|---|---|---|
| Firmware | Anwendungsimage, vollständiges 8-MiB-Flash-Image, Partitionen, Build-Manifest und Prüfsummen | [Öffnen](contrib/waveshare-esp32-c5-35/firmware/) |
| Quell-Snapshot | Vollständiger Snapshot-Patch und festgelegte Abhängigkeiten | [Öffnen](contrib/waveshare-esp32-c5-35/source/SNAPSHOT.md) |
| Board-Profil | TFT_eSPI-Displaykonfiguration und optionales Arduino-Board-Profil | [Öffnen](contrib/waveshare-esp32-c5-35/profile/) |
| Hilfsskripte | Reproduzierbarer Build, OTA-sicheres Flashen per USB und Installation des Board-Profils | [Öffnen](contrib/waveshare-esp32-c5-35/tools/) |
| Verdrahtung | Pin-für-Pin-Anschlussplan für Board und Display | [Öffnen](contrib/waveshare-esp32-c5-35/wiring/waveshare-c5-35inch-wiring.png) |
| Gehäuse | Druckbare STL-Dateien, Passform-Testteile und Druckhinweise | [Öffnen](contrib/waveshare-esp32-c5-35/enclosure/README.md) |
| Teileliste | Dokumentierte Komponenten des Aufbaus | [Öffnen](contrib/waveshare-esp32-c5-35/enclosure/PARTS.md) |
| Dokumentation | Build, Flashen, Validierung, bekannte Grenzen und Herkunftsnachweise | [Öffnen](contrib/waveshare-esp32-c5-35/docs/) |

<a id="de-hardware"></a>

## Hardware

| Komponente | Modell |
|---|---|
| Entwicklungsboard | Waveshare ESP32-C5-WIFI6-KIT-N32R8-UM |
| Display | Waveshare 3.5inch Capacitive Touch LCD |
| Displaycontroller | ST7796S |
| Touchcontroller | FT6336U |

Der [Verdrahtungsplan](contrib/waveshare-esp32-c5-35/wiring/waveshare-c5-35inch-wiring.png)
und die [Teileliste](contrib/waveshare-esp32-c5-35/enclosure/PARTS.md)
beschreiben den vorgesehenen Aufbau.

<a id="de-build"></a>

## Build und Flashen

Für die erste Installation und spätere USB-Updates gilt die
[Flash-Anleitung](contrib/waveshare-esp32-c5-35/docs/FLASH.md).
Das vollständige 8-MiB-Image startet bei Adresse `0x0`.
**Beim Flashen dieses Images wird der gesamte interne Flash-Speicher gelöscht.**

Der vollständige Waveshare-Quellstand wird über den
[Snapshot-Patch](contrib/waveshare-esp32-c5-35/source/SNAPSHOT.md)
auf der dokumentierten Upstream-Basis rekonstruiert. Die
[Build-Anleitung](contrib/waveshare-esp32-c5-35/docs/BUILD.md) beschreibt
den separaten temporären Worktree, die festgelegten Abhängigkeiten und
die Verwendung der [Hilfsskripte](contrib/waveshare-esp32-c5-35/tools/).

Der Ordner `esp32_marauder/` im Repository-Stamm bleibt auf der bisherigen
Upstream-Basis dieses Forks; er enthält **nicht** den rekonstruierten
Waveshare-Snapshot. Die Veröffentlichung des Pakets auf `master`
ist kein Rebase der Firmware auf den neuesten Upstream-Stand.

<a id="de-validierung"></a>

## Validierung und bekannte Grenzen

Alle 38 Paketdateien wurden unverändert aus dem
[ursprünglichen Paket-Commit](https://github.com/p-keminer/ESP32Marauder/commit/409f6b4e823734db142d7a935286030d300d2dfd)
übernommen.

Die veröffentlichte Binärdatei mit bereinigten Build-Pfaden wurde nicht
erneut auf die Hardware geflasht. Der unmittelbar vorhergehende Build
durchlief den dokumentierten Hardware-Test. Der veröffentlichte Snapshot
enthält außerdem die dokumentierte Änderung, die das Laufzeitpasswort
des SD-Dateimanagers in seriellen Diagnoseausgaben unkenntlich macht.

| Nachweis | Inhalt |
|---|---|
| [Validierung](contrib/waveshare-esp32-c5-35/docs/VALIDATION.md) | Dokumentierte Prüfungen und Hardware-Teststand |
| [Bekannte Grenzen](contrib/waveshare-esp32-c5-35/docs/KNOWN_LIMITATIONS.md) | Einschränkungen und nicht durch Tests abgedeckte Aussagen |
| [Herkunft](contrib/waveshare-esp32-c5-35/docs/PROVENANCE.md) | Herkunft und Zuordnung der Paketbestandteile |

Firmware und Funkfunktionen dürfen nur auf eigenen Systemen und Netzwerken
oder mit ausdrücklicher Berechtigung zum Testen eingesetzt werden.

<a id="de-lizenz"></a>

## Upstream und Lizenz

Dieser Fork basiert auf
[ESP32 Marauder von justcallmekoko](https://github.com/justcallmekoko/ESP32Marauder).
Die [ursprüngliche Upstream-README](README.upstream.md) und die
[MIT-Lizenz](LICENSE) bleiben erhalten.

<div align="center">

[![Nach oben](https://img.shields.io/badge/⬆_Nach_oben-24292f?style=for-the-badge)](#top)

</div>

---

<a id="english"></a>

<div align="center">

# ESP32 Marauder – Waveshare ESP32-C5

This fork publishes my own complete Waveshare package for the 3.5-inch
touch display on its default branch, `master`.

`ESP32-C5` · `C++` · `Arduino` · `PowerShell` · `3D printing`

</div>

<div align="center">

[![Open package](https://img.shields.io/badge/Open_package-24292f?style=for-the-badge)](contrib/waveshare-esp32-c5-35/README.md)
[![Overview](https://img.shields.io/badge/Overview-24292f?style=for-the-badge)](#en-overview)
[![Contents](https://img.shields.io/badge/Contents-24292f?style=for-the-badge)](#en-contents)
[![Hardware](https://img.shields.io/badge/Hardware-24292f?style=for-the-badge)](#en-hardware)
[![Build and Flash](https://img.shields.io/badge/Build_and_Flash-24292f?style=for-the-badge)](#en-build)
[![Validation](https://img.shields.io/badge/Validation-24292f?style=for-the-badge)](#en-validation)
[![License](https://img.shields.io/badge/License-24292f?style=for-the-badge)](#en-license)

</div>

---

<a id="en-overview"></a>

## Overview

The package brings together the firmware, complete source snapshot, board
profile, build and flash helpers, wiring diagram, and printable enclosure
parts for my Waveshare setup.

Start with the [package README](contrib/waveshare-esp32-c5-35/README.md)
for setup and usage. The linked technical documentation is currently
available in English.

<a id="en-contents"></a>

## Package Contents

| Section | Content | Direct link |
|---|---|---|
| Firmware | Application image, complete 8 MiB flash image, partitions, build manifest, and checksums | [Open](contrib/waveshare-esp32-c5-35/firmware/) |
| Source snapshot | Complete snapshot patch and pinned dependencies | [Open](contrib/waveshare-esp32-c5-35/source/SNAPSHOT.md) |
| Board profile | TFT_eSPI display configuration and optional Arduino board profile | [Open](contrib/waveshare-esp32-c5-35/profile/) |
| Helpers | Reproducible build, OTA-safe USB flashing, and board-profile installation | [Open](contrib/waveshare-esp32-c5-35/tools/) |
| Wiring | Pin-by-pin connection diagram for the board and display | [Open](contrib/waveshare-esp32-c5-35/wiring/waveshare-c5-35inch-wiring.png) |
| Enclosure | Printable STL files, fit-test parts, and printing notes | [Open](contrib/waveshare-esp32-c5-35/enclosure/README.md) |
| Parts list | Recorded components of the setup | [Open](contrib/waveshare-esp32-c5-35/enclosure/PARTS.md) |
| Documentation | Build, flashing, validation, known limitations, and provenance | [Open](contrib/waveshare-esp32-c5-35/docs/) |

<a id="en-hardware"></a>

## Hardware

| Component | Model |
|---|---|
| Development board | Waveshare ESP32-C5-WIFI6-KIT-N32R8-UM |
| Display | Waveshare 3.5inch Capacitive Touch LCD |
| Display controller | ST7796S |
| Touch controller | FT6336U |

The [wiring diagram](contrib/waveshare-esp32-c5-35/wiring/waveshare-c5-35inch-wiring.png)
and [parts list](contrib/waveshare-esp32-c5-35/enclosure/PARTS.md)
describe the intended setup.

<a id="en-build"></a>

## Build and Flashing

Follow the [flashing instructions](contrib/waveshare-esp32-c5-35/docs/FLASH.md)
for first installation and later USB updates.
The complete 8 MiB image starts at address `0x0`.
**Flashing this image erases the entire internal flash.**

The complete Waveshare source is reconstructed by applying the
[snapshot patch](contrib/waveshare-esp32-c5-35/source/SNAPSHOT.md)
to its recorded upstream base. The
[build instructions](contrib/waveshare-esp32-c5-35/docs/BUILD.md) cover
the separate disposable worktree, pinned dependencies, and use of the
[helper scripts](contrib/waveshare-esp32-c5-35/tools/).

The root `esp32_marauder/` directory remains the fork's existing
upstream baseline; it is **not** the reconstructed Waveshare snapshot.
Publishing the package on `master` does not rebase its firmware onto
the latest upstream release.

<a id="en-validation"></a>

## Validation and Known Limitations

All 38 package files are preserved unchanged from the
[original package commit](https://github.com/p-keminer/ESP32Marauder/commit/409f6b4e823734db142d7a935286030d300d2dfd).

The published path-sanitized binary was not separately hardware-flashed.
The immediately preceding build completed the documented hardware run.
The published snapshot also contains the documented change that redacts
the SD file manager's runtime password from serial diagnostics.

| Record | Content |
|---|---|
| [Validation](contrib/waveshare-esp32-c5-35/docs/VALIDATION.md) | Documented checks and hardware test status |
| [Known limitations](contrib/waveshare-esp32-c5-35/docs/KNOWN_LIMITATIONS.md) | Limitations and claims not covered by testing |
| [Provenance](contrib/waveshare-esp32-c5-35/docs/PROVENANCE.md) | Origin and attribution of package components |

Use the firmware and wireless features only on systems and networks you own
or are explicitly authorized to test.

<a id="en-license"></a>

## Upstream and License

This fork is based on
[ESP32 Marauder by justcallmekoko](https://github.com/justcallmekoko/ESP32Marauder).
The [original upstream README](README.upstream.md) and
[MIT License](LICENSE) are preserved.

<div align="center">

[![Back to top](https://img.shields.io/badge/⬆_Back_to_top-24292f?style=for-the-badge)](#top)

</div>
