# ESP32 Marauder — Waveshare ESP32-C5 3.5-inch package

This fork publishes p-keminer's complete Waveshare package on its default branch, `master`.

Supported hardware: **Waveshare ESP32-C5-WIFI6-KIT-N32R8-UM** with the **Waveshare 3.5inch Capacitive Touch LCD (ST7796S + FT6336U)**.

Start with the [Waveshare package README](contrib/waveshare-esp32-c5-35/README.md).

## Complete package

| What you need | Where to find it |
| --- | --- |
| Application and complete 8 MiB flash images, partitions, build manifest, and checksums | [Firmware](contrib/waveshare-esp32-c5-35/firmware/) |
| First installation and OTA-safe USB updates | [Flashing instructions](contrib/waveshare-esp32-c5-35/docs/FLASH.md) |
| Complete source snapshot and pinned dependencies | [Source snapshot](contrib/waveshare-esp32-c5-35/source/SNAPSHOT.md) |
| Reproducible build and helper scripts | [Build instructions](contrib/waveshare-esp32-c5-35/docs/BUILD.md) · [Tools](contrib/waveshare-esp32-c5-35/tools/) |
| Display setup and optional Arduino board profile | [Board profile](contrib/waveshare-esp32-c5-35/profile/) |
| Pin-by-pin wiring | [Wiring diagram](contrib/waveshare-esp32-c5-35/wiring/waveshare-c5-35inch-wiring.png) |
| Printable enclosure, fit-test parts, and parts list | [Enclosure](contrib/waveshare-esp32-c5-35/enclosure/README.md) · [Parts](contrib/waveshare-esp32-c5-35/enclosure/PARTS.md) |
| Recorded tests, known limitations, and provenance | [Validation](contrib/waveshare-esp32-c5-35/docs/VALIDATION.md) · [Limitations](contrib/waveshare-esp32-c5-35/docs/KNOWN_LIMITATIONS.md) · [Provenance](contrib/waveshare-esp32-c5-35/docs/PROVENANCE.md) |

Read the flashing instructions before writing an image: the merged image erases the complete internal flash.

## Source and validation

The complete Waveshare firmware source is supplied as a snapshot patch against the pinned upstream base recorded in [`source/SNAPSHOT.md`](contrib/waveshare-esp32-c5-35/source/SNAPSHOT.md). Follow the package's [build instructions](contrib/waveshare-esp32-c5-35/docs/BUILD.md) to reconstruct and build that source in a disposable worktree.

The root `esp32_marauder/` directory remains the fork's existing upstream baseline; it is **not** the reconstructed Waveshare snapshot. Publishing the package on `master` does not rebase its firmware onto the latest upstream release.

All 38 package files are preserved unchanged from the [package commit](https://github.com/p-keminer/ESP32Marauder/commit/409f6b4e823734db142d7a935286030d300d2dfd). The published path-sanitized binary was not separately hardware-flashed; the preceding build completed the documented hardware run. The published snapshot also contains the documented serial-password redaction. See the validation notes for the exact evidence and limits.

## Upstream project

Based on [ESP32 Marauder by justcallmekoko](https://github.com/justcallmekoko/ESP32Marauder). The [original upstream README](README.upstream.md) and [license](LICENSE) are preserved.

Use the firmware and wireless features only on systems and networks you own or are explicitly authorized to test.
