# STDF Cypher

**Fast, private STDF v4 analytics on your own PC.**
Open ATE test data and look at yield, bins, wafer and site maps, lots and retests, compare lots and testers, and screen for abnormal parts, in a desktop app or from the command line.
Everything runs on your PC and the app sends your data nowhere. Only `stdf-cypher serve --host <address>`, which you start yourself, lets other PCs on the network open the dashboard and the data it shows, without a password.

This repository holds the releases, the manual and the issue tracker.
STDF Cypher is freeware: free to use, also commercially, and free to share unchanged.

## Download

1. Download `stdf-cypher-<version>-windows-x64.zip` from the [latest release](https://github.com/izanorshahril/stdf-cypher-releases/releases/latest).
2. Extract it anywhere and double-click `stdf-cypher.exe`. There is no installer and no admin rights are needed.

The program is not signed, so Windows may show a SmartScreen warning for a downloaded copy: choose **More info**, then **Run anyway**.
Or unblock the zip before extracting it: right-click it, **Properties**, tick **Unblock**, or run `Unblock-File` on it in PowerShell.
Each release lists the zip's SHA-256 checksum in `SHA256SUMS.txt`.

Windows 10 or 11, 64-bit. The app opens in its own window using the Edge or Chrome engine already on the PC.

## What it does

- **Explore**: Lot summary (runs, passes and the final yield of a lot), Overview, Test explorer, Wafer maps, Site map, Part trail, Compare and Trace.
- **Investigate**: Drift report, Correlation, ANOVA, Abnormal parts and Machine learning.
- **Data and files**: Records, the part datalog, Edit and trim, Merge, split and export, and Match parts.
- **Command line**: `stdf-cypher --help` lists every command, from `info` and `split` to `report` and `anomaly`.

## Synthetic data only

STDF Cypher was built and tested without real STDF data.
Every STDF file used to build and test it was made from scratch by its own generator, `stdf-cypher synthetic-sample`, with made-up lots, parts and results.
None of them comes from a tester, a test floor or a real product.
Make such a file yourself with `stdf-cypher synthetic-sample out.stdf`.

## Manual

The manual is built into the app (**Help**, or F1) and is also online: [docs/manual](https://github.com/izanorshahril/stdf-cypher-releases/blob/main/docs/manual/README.md).

## Problems and ideas

Open an [issue](https://github.com/izanorshahril/stdf-cypher-releases/issues/new/choose).
Never attach STDF data from a test floor; try to show the problem with `stdf-cypher synthetic-sample` instead.

## Licence

See `LICENSE`. The open-source components built into the program keep their own licences: `THIRD-PARTY-NOTICES.md`. Both are in the zip and in [this repository](https://github.com/izanorshahril/stdf-cypher-releases).
Versions 0.3.22 and earlier were released under the MIT License.
See [CHANGELOG.md](https://github.com/izanorshahril/stdf-cypher-releases/blob/main/CHANGELOG.md) for what changed in each release.
