# Troubleshooting

## Where files are kept

| What | Where |
|---|---|
| Settings, recent files, saved cases, the theme and side-bar state | `%APPDATA%\stdf-cypher` |
| Copies of files dropped on the window, the window's browser profile | `%LOCALAPPDATA%\stdf-cypher` |

Deleting `%APPDATA%\stdf-cypher` resets the app to its first-start state.

## Common problems

**The window opens in a browser tab.**
Neither Edge nor Chrome was found, so the default browser is used. Everything works the same.

**"The STDF Cypher app has stopped."**
The app's server has ended, for example after the window was closed in another way. Start the app again.

**A page shows an error in red.**
Read the message: it is often the part filter. Clear the filter and try again. Other pages keep working.

**A page is missing from the side bar.**
It may be off in Settings, Pages, or experimental with the Experimental box off.

**A wafer map is empty or shifted.**
The file may not log PRR X/Y; set the wafer, X and Y tests and offsets in Settings, Die coordinates from tests.

**Parts are not matched across files.**
Check the IDs in Settings, Part identification, and the ID pickers on the page. Part IDs and X/Y restart in every file, so part text or wafer, X, Y match best.

**A file opened but has fewer parts than expected.**
A file cut off inside a part keeps that part without a bin; the Overview counts them as **Cut off**.

**The app is slow on a large file.**
Raise the threads in Settings, Opening files (0 uses every core). The status bar's resource monitor shows what the app uses.

## Report a bug

Open an issue on the [project's issues page](https://github.com/izanorshahril/stdf-cypher-releases/issues) (Help, **Report a problem**) with:

- the version (next to the name at the top of the side bar);
- Windows version;
- what you did, what you expected and what happened.

Never attach STDF data from a test floor. If a file is needed, try to show the problem with `stdf-cypher synthetic-sample` first.
