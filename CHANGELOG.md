# Changelog

Each release, newest first. Downloads are on the [releases page](https://github.com/izanorshahril/stdf-cypher-releases/releases).

## v0.4.4: File order, filter chips and marks (2026-11-24)

### Added
- **Filter chips**: the filters in use show at the top of the side panel, each with a **×** to take it out, plus **Clear all**. With no filter there is no chip. **+ Filter** adds good parts only, bad parts, parts with an alarm, sites, hard or soft bins, the first test of each part, or a custom filter.
- **Marked parts** in the side panel while a part is marked. Marks highlight a part on every chart and do not filter. Click a part to show it on another page, **×** to unmark it; **Undo** stays after the last one goes.
- **Sort Files** by your order, name or test time.
- **Reorder Files and Compare** with the up and down arrows on hover, or drag a file onto the top or bottom edge of another: a line shows where it goes, and a drop in the middle still groups them. Compare entries also move with Alt+Up and Alt+Down.
- **Good parts only** can be switched on or off from Search (Ctrl+K).

### Changed
- **Compare** takes up to 20 files or groups, tagged D1, D2… (D01, D02… with ten or more). With more open it compares the first 20 and says so. Past eight entries the cards above the charts sum up the yields, each entry's yield is listed beside it, the legend over the plot is left out, and repeated colours get square or diamond marks and dotted or dashed lines.
- **Compare filters**: an entry has no filter of its own; the side panel's filters and Filter by apply to every entry.
- **Box plot hover** shows only the statistic under the pointer, on its own box.
- **Banner**: only the page title. The active dataset is at the top of the side panel, where a click switches to another open file.
- **Files** stays at the top of the side bar, at most half the window high, with its own scroll; fold it to free the room.
- **Run tags** R1, R2… (R01, R02… with ten runs or more) on Part Trace and Retest recovery.
- **Part Trace**: the flow chart sits below the parts table and shows only with Experimental on.
- **Synthetic data only**: STDF Cypher was built and tested only with synthetic STDF files made from scratch by `stdf-cypher synthetic-sample`; the README now says so.

### Fixed
- Insight buttons and long card labels wrap in a narrow side panel instead of running off its edge.

## v0.4.3: Legends, Compare drag and warnings (2026-11-21)

### Added
- **Legends** on charts that compare layers (sites, files, groups; not the box plot): **Right** or **Left** over the plot, **Below** the axis, or **Off**, kept when you copy or save the chart. **Legend names** for files and groups: shortened, full, lot and step, or Dataset 1, 2, …
- **Drag into Compare**: drag files or groups from Files onto Compare. **Remove from compare** on their right-click menu takes one out; with fewer than two left, Compare goes back to automatic.
- **Compare warnings**: when tests matched as one differ in kind of result (parametric, multi-pin, functional) or in units, a warning above the charts counts them and the test list marks them ≠. The warning also names each entry's test program when they differ.
- **Overview splits**: **Split the bars by** site, CMOD, lot or file; the automatic choice is marked in the list. **Bins as** switches between Count and %.
- **Figures** in Test Explorer's Statistics picks what each layer shows: mean, sigma, min / max, median, Cp / Cpk and N.
- **Lot Summary** columns resize: drag a heading's right edge, double-click it to fit.

### Changed
- **Check for a new version** runs each time the app opens and stays silent offline; set it to **Check now** only in Settings, Updates. The version beside the app's name shines with a dot while a newer one is out.
- **Histograms and bars** of separate files compare in % of each, of one population (sites, bins) by count; the **%** / **Count** switch in the card header overrides it.
- **Labels** sit beside their controls.
- **Build the lot result** is offered only for a group with two runs or more that the recipe can combine.
- **Chipper** stays with no files open and says how to open some.

## v0.4.2: Compare, Part Trace and panes (2026-11-18)

### Added
- **Chart settings** on every chart card in Test explorer and Compare: bin size, 2D or 3D and depth, lines, opacity and axis range, in one button on the chart.
- **Enter opens a test**: type a test number or name in the test search and press Enter; with no exact match the nearest test opens.
- **Resizable panes**: drag the edge of the test list or the statistics, or minimize either to a strip.
- **Part jumps**: right-click a part on Test explorer, Compare, Part Trace or Part trail and choose **Show this part in** to open it on another page, marked.
- **Part Trace filters**: a filter per run (pass, fail, not tested or a hard bin), for example only the rejects of Run 2.
- **Add to compare** on a file's right-click menu.
- **Files grouping**: a file opened on its own joins the group of its lot ID, or of the file it shares the most part texts with; a merge makes a group of the merged dataset and its files.
- **Hard bins picker** in Lot summary for the bins not retested.
- **Check for a new version** (Settings, Updates): when you click Check now, or once a day by itself. Off by default; only the public releases page is asked.

### Changed
- **Compare** sits under Test explorer and works like it: tests on the left, one test's four charts with a layer per file or group, and the files or groups listed down the right with their statistics. With two Files groups or more it compares the groups, otherwise every file; a choice in Files takes over until **Back to automatic**.
- **Part Trace** (was Trace) traces the files Compare compares. The parts table has a column per run (Run 1, Run 2... with the file on hover) showing the hard bin; the failing tests are on hover and in the right-click menu.
- **Banner**: only the page title and, read only, the dataset, the parts and the filter. The part filter, the parts choice, Search and Help are at the top of the side panel, with icons when it is collapsed. Rename a dataset from its right-click menu.
- **Kill & catch**: the earlier run is the kill run and the later run the catch run; they start on the earliest and the latest file by test time.
- **Experimental**: Correlation, ANOVA, Abnormal parts, Machine learning and Marker search moved there.
- **Lot summary**: colour grades only pass 1 and the final result; later passes are faded and runs left out are grey. Bins not retested default to H2, H5 and H6.
- **Lines** between points are Show or Hide; until you pick, a trajectory has them and a trend does not.
- **Expand** fills the space between the test list and the statistics, and stays expanded when you pick another test.

### Fixed
- Chart cards overlapped after switching 2D and 3D, or lines on and off.

## v0.4.1: Compare, marks and lot recipe (2026-11-18)

### Added
- **Compare for many**: Compare takes two to eight files or groups (a file with a filter, such as site = 3) and puts every test side by side against the first one: each one's mean, spread and fail rate, how far it moved, and a PARTIAL flag when a file lacks the test. The former Compare is now **Marker search** under Investigate.
- **Files selection**: Ctrl+click, Shift+click or **Select** picks several datasets; right-click the selection to compare, merge, group or close it. The banner names the active dataset instead of a picker.
- **Kill & catch** (Investigate, experimental): follows the parts a test killed in a later run back to an earlier run by wafer, X, Y or part text, and ranks the earlier tests that could have caught them, with the best one charted beside the kill test. When too few parts link, or no test stands out, the page says so.
- **Chart cards** in Test explorer and Compare: each chart has a type menu, **Expand** to fill the page (Escape restores it) and **More** (collapse, copy, save as PNG, reset zoom, copy the test's number or name).
- **Copy charts as images** to the clipboard, from the chart toolbar or a card's menu.
- **Lines between points** on trend and trajectory charts, with their width and opacity.
- **Filter by** in Test explorer: good or bad parts, some hard or soft bins (or all but them), some sites, some part IDs (or all but them), the first or the last test of each part, odd or even parts, parts inside or outside the shown test's limits, or a filter of your own, on top of the banner's filter. The filter language gains `first_try`, `last_try`, `odd` and `even`.
- **Marked parts** in Test explorer: right-click a trend or scatter point to mark its part. It is crossed on every chart of the test, and in every other open file it is in (found by wafer, X, Y and part text), until you unmark it. Statistics lists the marks with Undo, Find in files and Clear all.
- **Copy a test's number or name** from any test table (right-click a row) and from chart cards.
- **Lot recipe** (Settings): pick the MIR fields runs must share to be one lot, for example lot, program and the step name in OPER_FRQ. Lot summary and lot results follow it, and a Files group gets one lot result per set of matching runs.
- **Field names** (Settings): rename the MIR fields shown in Lot summary, the lot recipe and Lot details.
- **Lot summary columns**: pick the MIR fields beside each run, now including the step name (OPER_FRQ) and the engineering ID.

### Changed
- **Engineering runs** (MODE_COD E) are left out of Lot summary's final result and of lot results unless you change their row.
- **Test explorer**: Layers by is now **Compare by**. The test you pick follows you to other files that have it.
- **3D** is for histograms only and is the default; the 2D/3D switch and a depth slider sit on each histogram.
- **Resource monitor**: its window shows a card per resource with a usage bar and the last two minutes.
- **Investigate pages** are marked experimental.
- **Chipper** (experimental) wears pixel sunglasses, a handlebar moustache and a chin beard.

### Fixed
- 3D line charts failed to draw, and three-digit colours were misread.

## v0.4.0: Fantastic (2026-11-18)

Codename **Fantastic**. A beta for early users; free for everyone.

### Added
- **Help**: the manual is built in. **Help** at the bottom of the side bar, **?** in the banner or F1 opens the section of the page on screen; its search box finds a word in every chapter, Ctrl+K lists its sections, and it links to this project's releases and issues.
- **Themes**: Workaholic (the new first-start theme) and Struggling, plus six experimental ones: Chill, Industry, Cybergeek (dot matrix, neon and glow), Classy (frosted glass and metal), Retronerd (pastel pop and 8-bit shadows) and Noir (greyscale).
- **Look settings** (Settings, Look): fonts for text and headings (a Nerd font, Cypher Sans, the dot-matrix Cypher Dot or Cascadia Mono), accent colour, glow, glass, corner radius, background texture and chart effects; chart colours as a set or one by one; gradients for heat maps and tables; and the thresholds that colour Cpk, yield and bin cells, with a "rule colours only" mode.
- **Lot details** on Home: set the lot, test step, program, CMOD and mode the app reads for a file, so a file with a missing or wrong MIR joins its lot. The STDF file is not changed.
- **Lot results**: a Files group of runs of one lot, step, flow and program with CMOD T, C, F or R gets the lot's final result as one more dataset, counted as Lot summary counts it.
- **Right-click menus** across the app: open files, switch dataset, go to any page, search, the theme; on a chart, reset zoom and save as PNG.
- **File groups**: datasets from one folder are grouped in Files; drag one onto another to group them, and rename, merge or close a group from its menu.
- **Chipper** (experimental): the helper now has a face that follows the pointer, shows what the app is doing, and mixes tips and sections of the manual in with facts about the data.
- **Resizable side bar and side panel**: drag their inner edge; the widths are kept.

### Changed
- **New icon.**
- **Files pane**: each file shows a short details line (parts as `1.4K`, lot, CMOD, program, step) that shows less as the side bar narrows.
- **Site map**: the layout follows each file's own sites; a layout you set applies to that dataset while it is open, and is no longer saved for every file with the same number of sites.
- **Licence**: from 0.4.0 STDF Cypher is freeware, free to use (also commercially) and to share unchanged; see `LICENSE`. Earlier versions stay under the MIT License. The open-source components keep their own licences, listed in `THIRD-PARTY-NOTICES.md`.

### Fixed
- **Combining files** whose fixed test limits differ (for example two program revisions) kept only the first file's limits; each file's parts now keep their own.

## v0.3.22: Files, monitor and scan records (2026-11-17)

### Added
- **Files** in the side bar: the open files and up to five recent ones, with a filter box; click one to switch to it.
- **Grouped side bar**: pages sit in groups that fold and stay as you left them. Shrunk to icons, the side bar shows one icon per group with a pop-out list of its pages.
- **Side panel** stays as a thin strip when hidden, with its own collapse button matching the side bar's.
- **Helper** (experimental): a dot-pattern character that follows the pointer, with a tip that changes every 10 seconds; a small one sits on the hidden side panel strip.
- **Resource monitor** in the status bar: CPU, memory, GPU and free disk, the app's own use and the whole PC's; hover for details. Settings can turn it off.
- **Scan records (STDF V4-2007.1)**: VUR, PSR, NMR, CNR, SSR, CDR and STR are read and shown in Records; STR filters by test number and appears in a part's record list.
- `synthetic-sample --profile tc --scan` writes scan records for testing.

### Changed
- Records with codes outside the standard are listed by code (for example `UNKNOWN 180/10`) instead of one UNKNOWN entry, and show their contents in hex.

## v0.3.21: New layout, side panel and search (2026-11-17)

### Added
- **New layout**: the top bar is gone. Pages are in a side bar with an icon each, and the arrow at its bottom shrinks it to icons only. Theme, light/dark and the **Experimental** box sit at the bottom of the side bar. A banner at the top names the page and holds the dataset, the population and the part filter. A status bar at the bottom lists the open files, parts, tests, size on disk, lots, steps and the filter in use.
- **Side panel** (button at the right of the banner): **Insights** lists ranked facts about the parts in scope, each from a fixed rule with its number (yield, top fail bin, most frequent first fail, a site or wafer at least 2 points under the rest, tests under Cpk 1.33), with a button to the page that shows more and *Filter to these*. **Scope** shows the dataset, population and filter, and the last ten filters to apply again.
- **Helper** (experimental, top of the side panel): tells one of those facts at a time (click it for the next) and answers a typed question about pages, tests and facts. Nothing leaves the PC.
- **Search** (Ctrl+K): pages and tabs, tests, recent filters and actions.
- **Experimental switch**: the Experimental box turns the experimental pages and the Helper on or off in one click; Settings, Experimental features, picks which ones it takes along. On by default.
- **New pages**: Site map, Part trail and Lot summary. Test explorer gains a 3D histogram and a normal probability plot.

### Fixed
- Settings, theme and side-bar state are kept by the app (`ui-state.json` beside its settings), so they survive a restart of the desktop app. Before, they could reset on every launch. Settings saved in the browser before move over on first start.

### Changed
- Every page is its own file, and Settings, Pages, can switch pages off. Old page addresses still open their page.

## v0.3.20: Label editor and Close all files (2026-11-12)

### Added
- **Label editor** (Settings, Labels): wafer, X, Y and the test label side by side. Each has one row to fill in (what goes before, between and after the numbers, or the test number and name), which writes the template under it; the template can also be typed freely. A check says what is wrong, and examples show the label and whether it reads back to the same die. Wafer, X and Y take any number of digits, X and Y also negative; with nothing between two numbers (`1118126`) X and Y are written as 3 digits. Clear a template to go back to the default.
- **Close all files** on Home: closes every dataset to start fresh. The files on disk are not changed.

### Fixed
- A label that would read back as another die is refused, e.g. a digit right next to a number (`{w}1{x}`).
- Both labels are saved together, so editing one quickly after the other no longer undoes it, and an invalid edit cancels a save still waiting.

## v0.3.19: One Trace page and trusted IDs (2026-11-12)

### Added
- **One Trace page.** The file list and ID checkboxes, run chips to drop runs in and out, **where the fails went** (click a box to list its parts), the followed test's value run by run, and the parts: per run pass / bin and the exact first and last failing test. Search finds part text, WXY, W,X,Y or a part ID in any run; click a part for its results in each run. CSV and the Excel report as before.
- **Most failed test first.** Charts of a test (Trace, Test explorer, Wafer maps, the Match dual view) open on the test most parts fail: the latest file when the files are one lot, else the highest fail rate.
- **Labels** in Settings: how wafer, X, Y and a test are written on every page, in reports and CSV, e.g. `W1_X118_Y126`, `1-118-126`, `1118126`, `T#72199_NAME`, `72199::NAME`, or your own template. Forms that cannot be read back are refused.
- **Part datalog** searches the single WXY test's value.
- **Command line:** `part-trace` takes `--show`, `--wxy-format` and `--test-format`.

### Changed
- **Trusted IDs.** Only PTR wafer, X, Y and PRR part text link parts across files, and wafer, X, Y decides when they disagree. PRR X/Y, the single WXY test and part ID are optional columns that never link (different values show as `a / b`): a single WXY test proved unreliable. ID order: W,X,Y, part text, X/Y, WXY, part ID; saved settings take it once.
- An ID value on several parts of one file (a copied memory, raw X/Y without offsets) is not used to match in that file; those tests are found by their other ID and marked.
- **Retest trace** leaves the Trace page; its recovery analysis is under Experimental as **Retest recovery**.
- Numbers are never written in scientific notation (`24111146`, not `2.411e+7`).

### Fixed
- Parts merged through another file count once, and "Last test only" applies to them.
- The ID audit no longer depends on the label format.
- Files without a lot ID are not taken for one lot.

## v0.3.18: Trusted IDs, saves and UX cleanup (2026-11-12)

### Changed
- **Part trace: the trusted ID decides.** When IDs disagree, wafer, X, Y (read from the part's own memory) decides over WXY, and both over part text (read by a camera as the handler picks the part, so it can land on the wrong part).
  - Same W,X,Y, other part text: one part, with red ID cells and an ID check note giving the other part text.
  - Same part text, other W,X,Y: two parts, side by side.
  - A W,X,Y on several parts (e.g. X and Y without their offsets) decides nothing, and an all-zeros or all-ones W,X,Y (0, 255, 65535, -1) matches nothing.
- **Saving:** every save button asks where with the Windows save dialog (or folder picker) and saves at once, in the last folder used. No path box.
- **Part datalog** shows wafer, X, Y from tests as logged, `W24X111Y146`, without offsets.
- **Records:** one browser by record type; PRR opens as the part table or as raw fields. The part datalog is the other tab.
- **ID pickers:** each page keeps its own choice, and each ID shows how many parts of that file have it. Unit correlation pairs parts with the same pickers as Match parts (was its own part ID / wafer + X/Y choice).
- **Retest trace → Bad candidates** hands over its own candidates (`$rt_bad_candidate`, found over the whole chain) instead of finding them again; `$rt_marginal` is now `$rt_passed_later`.
- **Part scope:** every export uses the part filter and the population and says which parts it writes; raw records, the part datalog, Find a part and Edit & trim say they read the whole file.
- **One editor per setting:** die X/Y tests and offsets and the loadboard test in Settings (pages show the value with a link); file opening options on Home.
- **Find a part** uses the part datalog's search; click a match for its results, add it to the part datalog, or show it in another file side by side.
- **Match parts** (was Match & merge) opens Split with matched / unmatched filled in.
- Settings typed on Merge, split & export are kept when you switch tabs; Home shows a few next steps instead of a list of every page.

### Fixed
- A file dropped on the window is no longer opened twice, and its temporary copy is deleted when its dataset or the window closes (not a day later).

## v0.3.17: Multi-ID part trace and new layout (2026-11-12)

### Added
- **Part trace by several IDs at once.** The Part trace report lists every ID with a checkbox: PRR part text (ULT), the WXY test, wafer, X, Y from tests, then part ID, wafer + X/Y and X/Y. Part text, WXY and wafer, X, Y are ticked when the files have them; untick one to leave it out of matching and of the report.
  - A part is found by any ticked ID, so one fills the gaps of another: an engineering file without part text finds its parts in a production file by WXY or wafer, X, Y, and a part that failed before its WXY test is found by its part text.
  - Each ticked ID is a column of the report, filled from whichever file has it.
  - **IDs that disagree are never merged.** A test with the same part text but another WXY keeps its own row, right after the other, with red ID cells and an **ID check** note. The page warns before the report is written.
- **Overview split by site.** With more than one site, the bin bars show the % of each site's parts and the yield by wafer and file has one bar per site.
- **Find a part** on the Trace page: one part by its ID, in one file or two side by side.
- **Instrument alarms** in GDR or DTR records are decoded and tied to their parts; Overview lists them and the filter field `inst_alarm` selects those parts.

### Changed
- **Wafer, X and Y read as `W12X-2Y25`** instead of `12|-2|25`, since `|` reads as "or" in a filter. On the die basis the ID holds die X and Y. Typing `12, -2, 25` still finds the part.
- **Side bar:**
  - **Explore:** Overview, Test explorer, Wafer maps, Compare and **Trace** (Part trace report, Retest trace, Find a part).
  - **Investigate** (was Statistics): **Drift report** (was Qualification drift), Correlation, ANOVA, Abnormal parts, Machine learning.
  - **Data & files:** Records (part table, **part datalog**, record viewer) and **Edit, merge & export** (Edit & trim, Merge, split & export, Match & merge).
  - **Experimental:** Failure investigation, Bad candidates, Signature check.
  - Old page addresses open their tab.
- Placeholder IDs (all zeros…) keep a row of their own in the part trace instead of sharing one.
- Synthetic sample data is named as such (`synthetic-sample`, `synthetic_samples/`) and has a TC STDF profile.
- **Command line:** `part-trace` takes `--key` more than once (default: part text, `--wxy-test` and `--wxy-tests`) and `--subtract-offsets`.

## v0.3.16 (2026-11-06)

### Added
- **Endurance auto trim.** Leaves out loops so the sites reach the yield threshold. A loop is the k-th part of every site (one touchdown), and a loop left out goes for every site.
  - **Ends:** the loops at the start and end in which any site fails (an unstable start, a degraded end).
  - **Ends, then bad loops between:** also the failing loops between, the loop failing on the most sites still below the yield first, until every site reaches it.
  - The trim leaves out at most 20% of the window's loops by default (0 = no limit). A site that cannot reach the yield within that, such as a broken site, is dropped and the trim runs again without it, so it never decides what the other sites lose.
- **Save trimmed STDF.** The compared sites from their first to last compared loop, without the trimmed loops, as a new STDF. The source file is not changed.
- The Sites sheet and the page show the loops trimmed and the yield of the kept loops; the title lines and Summary sheet list the loops left out.
- **Command line:** `endurance` takes `--trim off|ends|any`, `--max-trim` and `--trimmed-stdf`.

## v0.3.15 (2026-11-06)

### Added
- **Qualification drift page.** Mean drift of every test on every site, `ABS(mean1 - mean2) / (USL - LSL)`, exported to Excel. Each site holds its own looped unit, so each site is its own trial. Drift above 5% is red, Cpk below 1.33 is yellow, and a comment column says why.
- **Endurance check (one file).** The first 25 loops of each site against its last 25. Clean mode skips failing loops (an unstable start, noisy loops) and compares the first and last 25 good loops; a site below 95% yield over the compared span is dropped. The trial window can skip warm-up loops and end after 1,000 loops or 90 minutes, so loops of a run left going too long are left out. A site short of the loop or time target is dropped. Sheets: Drift, Sites, Summary.
- **25x loop compare (old vs new file).** Each site takes its first or last 25 good loops from each file; a site without 25 good loops in both files (unstable or inactive) is dropped, so no removing sites or trimming parts by hand. Tests pair by number and name, else by number and pin. Units that differ only by an SI prefix (mV and V) are converted. Sheets: Mean drift, Sites, Unmatched tests, Summary.
- Both reports show N for each statistic, use the limits of the compared loops for tests whose limits change part by part, and keep test-site rows that have no values on one side.
- **Command line:** `endurance` and `loop-compare`.

## v0.3.14 (2026-11-04)

### Added
- **PTR tests as part IDs, in one order.** Every page that identifies parts now lists PRR part text (ULT), the WXY test (80149), the wafer + X + Y test combination (80100, 80101, 80102), then part ID, wafer + X/Y and X/Y. The first usable one is the default.
- **ID audit in Part trace.** Checks that part text, WXY and wafer, X, Y agree for the same part, in each file and across files: one part text with two WXYs, one WXY or W|X|Y on two part texts, or a WXY that is not its own W|X|Y. A missing value is not a problem, since a part can fail before those tests. The page warns, the part's cell is red in the report, and an **ID audit** sheet lists every test involved. Matching itself does not change.
- **Part trace offers the next ID** when the chosen one finds no shared parts. A file that does not log the chosen tests no longer stops the trace: its parts are left out and counted.
- **Warning for IDs above 16,777,216.** STDF stores PTR results as 32-bit floats, so such a code is rounded and different parts can share it.
- **Command line:** `part-trace` takes `--wxy-test`, `--wxy-tests` and `--offset-tests`.

### Changed
- **Settings:** Part identification is one ordered list with ↑ ↓ and the test numbers in it. Die coordinates and other trace fields have their own sections. A default you saved before stays first.

## v0.3.13 (2026-11-04)

### Added
- **Part trace** (under Investigate): each part's history across STDF files, exported to Excel. One row per part, by part text or another ID, and one group of columns per file: part ID, hard bin, site, first and last failing test. Failing bins are red, and a Summary sheet lists each file with its lot, tester and counts.
- **Shared parts are detected.** Open files that hold the same parts are ticked for you, and Home offers the page. Files can be in any order and from any lot: a part shows in every file that holds it and the other columns stay blank. Sort the files and rename them for the report.
- **Same part twice in one file:** you get a warning, and each extra test takes one more row. For intended repeats, such as an engineering file, tick **Last test only** for that file to keep each part's last test.
- **Command line:** `stdf-cypher part-trace FILES -o trace.xlsx [--key part_txt] [--names A,B] [--last-only all|1,3]`.

## v0.3.12 (2026-11-03)

### Fixed
- **Edit & trim: quota is per site.** The number you enter is the number of good parts taken from each ticked site, in file order. In 0.3.11 it was one total spread over the sites, which was wrong. A site with fewer good parts than the number gives all it has, and the prompt asks whether to drop it (yes or no).
- The quota's wording now says per site.

## v0.3.11 (2026-11-03)

### New
- **Edit & trim: quota pick.** Choose N good parts and they are spread evenly over the sites you tick, taken in file order. Each site's allocation is shown before you apply it. A site with fewer good parts than its share asks whether to drop it (yes or no). With no, the site keeps the parts it has.
- **Edit & trim: one selection.** The selection is shown at the top, with its good, bad and cut-off counts. Three ways to pick (by numbers, by rules, quota) preview their parts before one operation applies them: replace, add to, or take out of the selection. Sites are ticked in the yield table, and the rules and the quota use them.
- **Save with an arrow.** Save only, or Save and open in the app. Merge and extract use the same save button.

### Changed
- Opening files from Home keeps you on Home, so you choose the page yourself.
- Edit & trim: the search only finds parts and no longer changes the selection. The result label reads "all results (incl. cut off and unknown)".

### Notes
- The quota takes parts in file order within each site. Tell us if you want a spread across the file instead.

## v0.3.10 (2026-11-03)

### New
- **Touchdown and loop (experiment, off by default).** Switch it on under Settings, Experiments.
  - **Touchdown:** the parts tested together. Found from the PIR runs of the file when it has them, otherwise from the site order and the test times (the parts of a touchdown finish together). The numbering starts at 1, or at 0 if you set it so.
  - **Loop:** how often the same part ID (or part text) has come up before in the file, e.g. one DUT set tested again on every loop. Choose which one counts, or none.
  - **Records** shows a touchdown summary (sites, parts, good, bad, median test time, loops) and Touchdown and Loop columns.
  - **Edit & trim** shows the same columns and can select by touchdown.
- **Edit & trim: yield by site.** Each site's good, bad and yield, with a Select and an Only this site button. A site more than 10 points below the file's yield is flagged. The file's total is shown underneath.
- **Edit & trim: select by result, site and touchdown.** Good only, bad only or both; any sites ticked (none ticked = all); touchdowns as numbers and ranges (`3-5,9`). The conditions combine.
- **Dummy touchdown file.** `stdf-cypher sample demo.stdf --touchdowns 30 --sites 8` writes a file with the same DUT set on every loop, a weak site 3 and touchdown structure, for trying the experiment without a real file. Add `--no-pir-runs` to test the fallback that has no PIR runs.

### Notes
- The touchdown estimate is not validated on real tester files. The dummy file is the only test data: on it the estimate matched every planted touchdown, with and without PIR runs. Check it against your own records before relying on it.
- Records and Edit & trim show the experiment only while it is switched on.

## v0.3.9 (2026-11-03)

### New
- **Edit & trim.** Keep or remove parts of a file and save the result as a new STDF. The file you opened is not changed.
  - Pick parts by part ID or row number, with ranges and lists such as `1-3,5,2000-2012`, by a filter, or any mix.
  - The dashboard lists every part of the file: click, Ctrl+click and Shift+click pick parts. A summary says how many parts will be written, how many are good and where the part IDs will run.
  - Part IDs stay as they are, or are backfilled to run 1…N.
  - The output is `.stdf`, or `.stdf.gz` when the name ends in `.gz`. It is written to a temporary file and moved into place when complete.
- **CLI:** `stdf-cypher trim FILE --keep 1-3,5 --renumber -o out.stdf`. Use `--remove` instead of `--keep` to drop the listed parts, `-f` to add the parts a filter matches, and `--by row` to count rows instead of part IDs.

### Fixed
- Split: datalog (GDR and DTR records) follows the part before it. The notes of a part that is not written no longer appear in the other outputs.
- Split: a part cut off before its PRR at the end of a file is kept, instead of being dropped.

### Notes
- Bin and pass/fail summaries are regenerated for the parts written. TSR (test synopsis) records are still not written by split or trim.

## v0.3.8 (2026-10-29)

### New
- **Parallel reading.** One file is read on several cores. Records are built in chunks and merged in file order, so the result is the same as a one-thread read. Set the threads with `--threads`, `STDF_CYPHER_THREADS` or Settings > Opening files (0 = one per core).
- **More inputs.** `.bz2` and `.zip` files are read as well as `.gz`. A zip holds one STDF file, and each entry is checked against its CRC-32 and size.
- **xlsx export.** `stdf-cypher xlsx FILE -o out.xlsx` writes every record to an Excel workbook, one sheet per record kind. Sheets continue past 1,048,575 rows.
- **Test list.** Cpk is amber below 1.33 and red below 1.00, and tests with failing parts are shown in red.
- **Box select.** On any chart, the box select lists the parts in the selection, with a CSV download.
- **Limits and datalog.** A PTR whose own limits differ from the test's keeps them per part, and the trend draws them as per-part limit lines. GDR and DTR records are kept with the part they follow and listed in the Overview.
- **Retest trace.** Each trace test has a trace box: untick a test the program does not log. The WXY test is checked against the raw wafer, X and Y, or against die X and Y when set to die.
- **Incomplete files.** A file cut off inside a part keeps that part with its results and no bin or verdict. The Overview shows a Cut off count, and the CLI prints a warning.

### Notes
- The dashboard answers only its own address and page, with a token made at each launch. `serve --host <address>` lets another PC open it.
- Settings saved before this version move a WXY test of `500` to `80149` once.

## v0.3.7 (2026-10-27)

### New
- **Retest trace: ID audit**. WXY and part text should each belong to one part; the audit finds where they don't.
  - **Within a run:** one WXY on parts with different part texts (e.g. a corrupt EEPROM reading all zeros), one part text on parts with different WXYs (a 2D code misread or copied), and placeholder values (all zeros, all ones, one character repeated).
  - **Between runs:** **link changed** (found by WXY, but with another part text than before: camera out of sync or a wrong sort), **key conflict** (its part text is on a row with another WXY, not joined) and **ambiguous** (its own ID is on several parts there, so it is not matched rather than guessed).
  - Shared and placeholder values are kept out of matching in the runs they are found in when the other ID can match instead, so they never merge different parts. Before, 20 parts with WXY 0 would collapse into one.
  - A part keeps its first IDs; a changed part text is flagged, not taken over.
- **How to see it:**
  - An **ID audit** section with counts, a chart of problems per run and a table of them; click a row to highlight its part.
  - An **ID check** column in the parts table, and the part set `$rt_id_issue` in every run.
  - An **ID trail** for the highlighted part: its WXY and part text in every run, how it was found (start, key, link, not joined), bad values struck through and changed ones marked.
- The audit needs a link (**Then link by**) to compare the two IDs; without one, only placeholder values are found.

## v0.3.6 (2026-10-27)

### New
- **Retest trace: Then link by** (default part text): a second ID that keeps following a part where its key is missing.
  - Example: WXY is logged in runs 1 and 2, but the part fails before the WXY test in runs 3 and 4. It is now still found in runs 3 and 4 by the part text it had in the last run it was found in.
  - The link never joins two rows whose keys are both present and different, and never takes a row another part matched by key.
  - A run whose file has no WXY test at all no longer stops the trace; that run is matched by the link alone.
  - Run-1 parts without a WXY are traced by part text and pick up their WXY from a later run.
  - **Matched by** shows how many parts the link found, and the parts table has a **Linked in** column (e.g. `R3, R4`).
  - Pick **nothing (key only)** to trace by the key alone, as before.

## v0.3.5 (2026-10-23)

### New
- **Settings > Part identification and trace**: one section for everything that identifies or traces a part.
  - **Part trace**: wafer, X, Y and X/Y offset tests (for wafer reconstruction), plus a single **WXY** test (wafer, X and Y in one result).
  - **Other trace**: test program revision, loadboard, and any **other IDs** you add (name + test).
  - **Ignore the identification tests in analytics**: one checkbox keeps all of these out of marker rankings, signatures and first-fail picks. It replaces the "Leave out tests" boxes in Settings, Compare, Bad candidates, Signature check, Failure investigation and Retest trace; tests from your old list carry over as other IDs.
  - PRR part ID, part text, X/Y and wafer are always available for tracing.
- **Retest trace**:
  - Clicking a part on a chart highlights it and narrows the parts table to it, without opening the trace or scrolling away. **Trace this part** opens the trace when you want it; clicking a row in the table still traces as before.
  - **Find part** above the flow and trajectory charts does the same from typed text: part key, part text, part ID, WXY, other IDs, or wafer|X|Y (e.g. `1|-7|-10` or `1 -7 -10`). Several matches are listed to pick from.
  - A **trace card** shows the highlighted part's trace fields; pick which ones with **Fields** (e.g. part text and WXY). The choice is remembered.
  - The parts table search matches the same trace fields.

## v0.3.4 (2026-10-22)

### Improved
- **Retest trace**:
  - Click any line or point on the trajectory or run-to-run chart to highlight that part. It gets a thick line (or a ring), the other parts fade, its row is selected in the parts table and its trace opens. Click it again to clear it.
  - A bar above the chart names the highlighted part with **× clear**.
  - **↺ Reset view** clears the highlight, the trace, the table search and every chart zoom.
- **Every view with a clickable table** (Compare, Abnormal parts, Records, Match & trace, Bad candidates, Correlation): click the selected row again, or use **× Clear selection**, to close what it opened.
- Part detail and trace panels have a **× Close** button.

## v0.3.3 (2026-10-22)

### New
- **Merge** (on *Match, merge & trace* and *Merge, split & export*): open files of the same lot and test step are offered for merging. Any parts they share are reported but don't block the merge. Set the file order, and optionally renumber part IDs so each file continues from the previous file's last ID. Then combine them in the app or save one merged STDF.
- **Part datalog**: find parts by part ID, X/Y, part text or die X/Y read from tests. Live top-3 matches add parts and tests in one click, and you can paste a list. Give each part a mark (the label on the physical unit) and reorder the list. Save as readable text or CSV; tests a file lacks print as N/A.
- **Settings** page: file order, retest handling, part identity, tests left out of rankings, loadboard test, the tests that hold die X/Y, chart defaults and theme.
- **Charts**: a bin-size slider on every histogram. Test explorer shows the box plot under the histogram on one axis, and Compare adds box plots of the top tests, A and B side by side.
- **Themes**: Default, Industry, Office and Work, each in light and dark.

### Improved
- The side menu is grouped (Explore, Investigate, Statistics, Data & files), the home page lists every view, and the test list is wider.
- Saving recent files from several windows at once no longer loses the list.

## v0.3.2 (2026-10-22)

### New
- **Retest trace**: follow parts through a chain of up to 8 runs and more, covering reject retests and retests of good parts.
  - Each part's site is shown in every run and in the hover hints.
  - **Pass/fail by test site** summary per run, with a chi-square p-value.
  - Parts that pass the traced test but fail another test or carry an alarm show in yellow.
  - **Bad candidates from the retests of good parts**, with an inline candidate-test ranking and a jump to Bad candidates.
- **Signature check** and **Failure investigation** pages.
- **Test explorer**: tick or untick groups in *Statistics by group* to show or hide them on the charts.
- **Open folders**: drop a folder, drop it on the exe, or use *Open folder…*. Only STDF files are loaded. Opened files sort by test start time or file name (a setting on the home page).
- **Several windows**: every launch of the exe is its own instance with its own files. Recent files are shared safely between windows.
- Sample generator: `--extra-test`, repeatable `--band-test` and `--latent-test`.

### Fixed
- `serve` picks a free port when 8765 is taken.
- Retest trace flow chart no longer shows "undefined" nodes.

## v0.3.1 (2026-10-21)

## What's new in 0.3.1

- **Bad candidates** view: match the bad parts of file 2 (optionally only those failing one test) to the good parts of file 1 by part text, and mark them as `$bad_candidate` in file 1 without splitting anything. It profiles them against the other good parts with:
  - a plain-language summary
  - the focus-test ranking, with charts
  - outlier indicators (robust z, PAT, NNR, Mahalanobis, Isolation Forest, ±3σ count)
  - common factors (site, wafer, wafer zone, stepping-field position, bins, lot, alarms)
  - a stacked candidate-rate wafer map
  - a per-candidate list
- Marker ranking adds **PAT** and **ANOVA** (p, η²), and can leave out identity tests (e.g. `500, 80100-80104`). The Compare tab has a "Leave out tests" field.
- Compare and Bad candidates histograms switch between **% of group** and **counts**.
- Hover notes on every method column, plus a "Methods and how the score is calculated" panel.

## Install

## v0.3.0 (2026-10-21)

Windows x64 build of commit 1d94117. Download `stdf-cypher-0.3.0-windows-x64.zip`, extract it anywhere and double-click `stdf-cypher.exe` (no installer, no admin rights).

New:
- **Marker candidates** in Compare: every test ranked immediately (separation/AUC, ±3σ tails, random forest weighted by model skill; with the same units in a second file also drift, residual and correlation break). Top-10 lists, top-candidate overlays, CSV.
- **Match & trace**: quick filters for good/bad/bin-1 parts failing a test, *Find marker tests*, matched/unmatched datasets → Compare.
- **Filters**: `fail(1013)`, `first_fail = 1013`, `n_fails`.
- **Wafer maps from logged tests** with offsets: defaults 80100–80104, add/subtract offset, flip X/Y.

SHA-256 of the zip in `stdf-cypher-0.3.0-windows-x64.zip.sha256`.

## v0.2.0 (2026-10-21)

Windows x64 build of commit 7f9eb02. Download `stdf-cypher.exe`, copy it anywhere and double-click it (no installer, no admin rights).

Highlights: Records view (part table + raw record viewer), Match & trace across two files (PART_TXT, part ID, X/Y or datalogged PTR keys; part sets, dual charts, unit trace, matched/unmatched split), split by PTR value or part list, dataset rename, good-parts population, axis range / colouring / 2D-3D / opacity chart options, wafer maps rebuilt from logged wafer/X/Y tests.

SHA-256 in `stdf-cypher.exe.sha256`.

