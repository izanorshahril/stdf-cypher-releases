# Files and datasets

A **dataset** is what the pages work on: one STDF file, or several files combined.
The banner's Dataset picker chooses the active one.

## Files pane

The **Files** group in the side bar lists the open datasets.
A dataset of several files shows them under its arrow, and the active dataset is marked.
Click a dataset to switch to it: it becomes the active dataset, named in the banner, and the pages show it.

## Selecting several

- **Ctrl+click** adds a dataset to the selection or takes it out; **Shift+click** adds every dataset between the last one picked and this one.
- **Select**, next to the filter box, shows a tick box on every dataset, to pick several without the keyboard; **Done** hides them.
- With two or more selected, a bar above the list offers **Compare** and **Merge into one dataset**; **…** adds **Group them**, **Close** and **Clear the selection**, and so does a right click on any selected dataset.
- Compare takes the selection as its entries, in the order they were picked.

Under each name is a short details line: parts (`1.4K` is about 1,400), lot, CMOD, program and test step.
The narrower the side bar, the fewer of them it shows; parts and lot always stay.
Hover a dataset for all of them, with the mode and the full part count.

The filter box matches file names, paths, lots, steps and group names.
Recent files (up to five) can be opened again from here, or forgotten from their right-click menu.
In the shrunk side bar, the Files icon opens the pane in a flyout.

## Groups

Datasets from the same folder form a group named after the folder; a dataset alone is listed on its own.
Dropping several folders on the window groups each folder's files.

- Drag a dataset onto another to group the two.
- Drag a dataset onto a group to add it.
- Drag a dataset onto *Drop here to take it out of its group* to take it out.

Groups are labels in the app only: no file is moved, copied or renamed.

Right-click a dataset to switch to it, open it on a page, compare it, rename it, edit its lot details, move it to a group, show it in its folder or close it.
Right-click a group to fold, rename, merge, build its lot result, ungroup or close it.

## Lot results

The runs of a group that share the fields of Settings, Lot recipe (lot, test step, flow and program by default), each with CMOD T, C, F or R, get one more dataset at the group's top, marked **LOT**: the lot's final result, built by its recipe.
A group holding runs of two steps gets one lot result for each.
Engineering runs (MODE_COD E) are left out.

- Pass 1 is the first run (T) with its continuations (C); each retest of rejects (F) starts the next pass; a 100% retest (R) starts the count over.
- Every good part of every pass is kept.
- A bad part in a bin that is not retested (**Bins not retested** on Lot summary) is kept from whichever pass.
- Every other bad part is kept from the last pass only, because the earlier ones went on to a retest.

These are the parts the Lot summary counts as the lot's final result, so its yield matches.
The runs stay open on their own.
The lot result is built when the group first matches, and built again when a run is added to the group; **Build the lot result** in the group's right-click menu builds it again or says why the group does not match.
Closing a run closes its lot result.
Settings, Opening files, turns the automatic build off.

## Lot details

A file with a missing or wrong lot, step, program, CMOD or mode in its MIR can still join its lot.
**Lot details** on Home lists every open file with these five values: a grey value is the file's own, and a value you type replaces it in the app.
The STDF file is not changed, but every page reads the new values: Overview, Lot summary, the Files pane, merging and the part filter (`lot = ...`).
**Edit lot details** in a dataset's right-click menu opens Home at that file.
After a change, a lot result the change undoes (a CMOD changed, say) is built again.
While an analysis is still reading the file, saving waits a few seconds and then says so, with nothing changed; save again when it finishes.
Another app window uses the new values for files it opens after the change.

## Combining and merging

Files opened together can be combined into one dataset (set on Home, next to where files are opened).
Files of the same lot and test step are offered for merging on **Merge, split & export**, where they can also be saved as one merged STDF.
See [Pages](04-pages.md#merge-split--export).

## Order of opened files

**Order of opened files** on Home sorts files by test start time (the default) or by file name.
This sets the run order on Trace.

## Renaming

The pencil button next to the Dataset picker, or *Rename* on Home or in the Files pane, renames a dataset.
The name is used in Compare, Match parts and chart titles; the file on disk keeps its name.

## Closing

Close a dataset from Home or its right-click menu, or use **Close all files** on Home to start fresh.
The files on disk are not changed.

## Dropped files

A browser gives the page a dropped file's contents but not its path, so a file dropped on the window is opened from a copy in `%LOCALAPPDATA%\stdf-cypher\uploads`.
The copy is deleted when its dataset is closed or the window closes; a copy left by a crash goes a day later.
Ctrl+O, Recent files and files dropped on the `.exe` are read in place.
Uploads are stored up to 8 GB each.
