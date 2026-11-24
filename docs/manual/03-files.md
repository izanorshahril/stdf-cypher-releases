# Files and datasets

A **dataset** is what the pages work on: one STDF file, or several files combined.
Files chooses the active one; the top of the side panel names it.

## File pane

The **File** group in the side bar lists the open datasets.
A dataset of several files shows them under its arrow, and the active dataset is marked.
Click a dataset to switch to it: it becomes the active dataset, named at the top of the side panel, and the pages show it.
The list stays at the top of the side bar while the pages under it scroll, and takes at most half the window's height; a longer list scrolls on its own.

## Order

**Sort** at the top of the list lists the files in **your order**, by **name** or by **test time** (the start time in the file).
Your order starts as the order the files were opened in.

- Hover a file or a group for its up and down arrows (Tab reaches them too): a file moves among the other files of its group, or among the files and groups at the top; a group moves as a whole. A group's lot result and merged dataset stay at its top.
- Drag a file onto the top or bottom edge of another: a line shows where it goes, and it is put there, in that file's group or on its own.
- Moving a file while the list is sorted by name or time sorts it in your order from then on, starting from the order shown.

Compare's automatic entries follow this order (D1 is the first).
Your order lasts while the app window is open.

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
Untick **Auto group** at the top of the list to keep only the groups you make yourself; tick it again to group by folder, lot and part text.
A file opened on its own, from another folder or dragged in later, joins the group of the open files of its lot ID; without a lot ID in common, the group of the file it shares the most part texts with.
Files of one lot that are each on their own form a group named after the lot.
A file you placed or took out by hand stays where you put it.
**Merge into one dataset** makes a group of the merged dataset, listed first, and the files it was made of; no lot result is built for that group.

- Drag a dataset onto the middle of another to group the two.
- Drag a dataset onto a group to add it; onto the top edge of a group's heading to put it just above the group, on its own.
- Drag a dataset onto *Drop here to take it out of its group* to take it out and put it at the end of the list.

Groups are labels in the app only: no file is moved, copied or renamed.

Right-click a dataset to switch to it, open it on a page, compare it or add it to Compare, rename it, edit its lot details, move it to a group, show it in its folder or close it.
Right-click a group to fold, rename, merge, build its lot result, ungroup or close it.
**F2** renames the file or group that has focus in Files; after a click on a file, it renames that file, the active dataset.

## Lot results

The runs of a group that share the fields of Settings, Lot recipe (lot, test step, flow and program by default), each with CMOD T, C, F or R, get one more dataset at the group's top, marked **LOT**: the lot's final result, built by its recipe.
A group holding runs of two steps gets one lot result for each.
Engineering runs (MODE_COD E) are left out.

- Pass 1 is the first run (T) with its continuations (C); each retest of rejects (F) starts the next pass; a 100% retest (R) starts the count over.
- Every good part of every pass is kept.
- A bad part in a bin that is not retested (**Bins not retested** on Lot Summary) is kept from whichever pass.
- Every other bad part is kept from the last pass only, because the earlier ones went on to a retest.

These are the parts the Lot Summary counts as the lot's final result, so its yield matches.
The runs stay open on their own.
The lot result is built when the group first matches, and built again when a run is added to the group; **Build the lot result** in the group's right-click menu builds it again; the menu offers it only for a group with two runs or more that the recipe can combine.
Closing a run closes its lot result.
Settings, Opening files, turns the automatic build off.

## Lot details

A file with a missing or wrong lot, step, program, CMOD or mode in its MIR can still join its lot.
**Lot details** on Home lists every open file with these five values: a grey value is the file's own, and a value you type replaces it in the app.
The STDF file is not changed, but every page reads the new values: Overview, Lot Summary, the File pane, merging and the part filter (`lot = ...`).
**Edit lot details** in a dataset's right-click menu opens Home at that file.
After a change, a lot result the change undoes (a CMOD changed, say) is built again.
While an analysis is still reading the file, saving waits a few seconds and then says so, with nothing changed; save again when it finishes.
Another app window uses the new values for files it opens after the change.

## Combining and merging

Files opened together can be combined into one dataset (set on Home, next to where files are opened).
Files of the same lot and test step are offered for merging on **Merge, Split & Export**, where they can also be saved as one merged STDF.
See [Pages](04-pages.md#merge-split--export).

## Order of opened files

**Order of opened files** on Home sorts files by test start time (the default) or by file name.
This sets the run order on Part Trace.

## Renaming

The pencil button next to the Dataset picker, or *Rename* on Home or in the File pane, renames a dataset.
The name is used in Compare, Match Part and chart titles; the file on disk keeps its name.

## Closing

Close a dataset from Home or its right-click menu, or use **Close all files** on Home to start fresh.
The files on disk are not changed.

## Dropped files

A browser gives the page a dropped file's contents but not its path, so a file dropped on the window is opened from a copy in `%LOCALAPPDATA%\stdf-cypher\uploads`.
The copy is deleted when its dataset is closed or the window closes; a copy left by a crash goes a day later.
Ctrl+O, Recent files and files dropped on the `.exe` are read in place.
Uploads are stored up to 8 GB each.
