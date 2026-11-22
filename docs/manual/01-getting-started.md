# Getting started

## Install

Download `stdf-cypher-<version>-windows-x64.zip` from the [releases page](https://github.com/izanorshahril/stdf-cypher-releases/releases), extract it anywhere and double-click `stdf-cypher.exe`.
There is no installer and no admin rights are needed.

The program is not signed, so Windows may show a SmartScreen warning the first time it runs a downloaded copy: choose **More info**, then **Run anyway**.
Or unblock the zip before extracting it: right-click it, **Properties**, tick **Unblock**, or run `Unblock-File` on it in PowerShell.

The app opens in its own window using the Edge or Chrome engine already on the PC.
If neither is installed, it opens in your default browser and works the same way.
Windows briefly shows a console window before the app hides it.

## Open files

- **Open** at the top of the side bar (Ctrl+O) opens the Windows file dialog; right-click it for **Open a folder…**.
- Drag files or folders anywhere onto the window.
- Drop files onto the `stdf-cypher.exe` icon, or set it as the "Open with" program for `.stdf`.
- Pick one from **Recent files** on Home or in the File group of the side bar.

STDF Cypher reads `.stdf` and `.std` files, also compressed as `.gz`, `.bz2` or `.zip` (a zip holds one STDF).
A folder opens every STDF file in it and its subfolders; other files are skipped.
A file that is already open is not opened again.

A file cut off inside a part keeps that part, with its results but no bin and no pass or fail verdict.
The Overview shows a **Cut off** count, so a lost PRR is never silent.

## Try it without data

The `synthetic_samples` folder holds made-up files, not from a tester:

- three wafer-sort demo files: a lot, a shifted lot, and the same lot tested again on a second tester;
- looped final-test files for the Drift Report.

Each comes in the plain and the custom test-cell (TC) profile.
You can make more with `stdf-cypher synthetic-sample` (see [Command line](08-command-line.md)).

## A first look

1. Open a file. Home lists it under **Open datasets** and offers **Next steps**.
2. Open **Lot Summary** for the runs and yields, or **Overview** for bins and fail pareto.
3. Click a test in the fail pareto to open it in **Test Explorer**.
4. Type a part filter at the top of the side panel, such as `site in (1,2)`, and every page follows it.

## Several windows

Each launch, by double-click or by dropping files on the `.exe`, opens its own window with its own files and pages.
Selecting several files and choosing "Open with" opens them together in one window.
Recent files and saved cases are shared between windows.

## Quit

Close the window. The app exits by itself a few seconds later.

## The dashboard in a browser

`stdf-cypher serve lot.stdf` starts the same dashboard at `http://127.0.0.1:8765`.
It answers only its own address and its own page: each launch makes a new token that the page sends with every request, so other websites and other PCs cannot read or drive it.
`serve --host <this PC's address>` also accepts that address, so another PC can open it.
Then anyone who can reach that address can open the dashboard and the data it shows, without a password: use it only on a network you trust.
