# Pages

Every page uses the dataset, the population (all parts or good parts only) and the part filter of the side panel, all named in the banner, unless it says otherwise.
Raw records, the part datalog, Find a part and Edit & trim work on the whole file and say so.

A page or tab has its own address, such as `#records/datalog`, and old addresses such as `#parttrace` still open their page.
Settings, Pages, removes a page you do not use from the side bar.

## General

### Home

Home opens files (dialog, drag and drop, recent files or a typed path) and lists the open datasets, each with **Analyse** and **Close**.
**Close all files** starts fresh; the files on disk are not changed.
The order of opened files, retest handling and combining files are set here, next to where files are opened.
**Lot details** sets the lot, test step, program, CMOD and mode the app reads for each open file (see [Files and datasets](03-files.md#lot-details)).
**Next steps** offers a few pages that fit what is open.
Opening files from Home keeps you on Home.

### Help

This manual.
The list on the left opens a chapter; the search box finds a word in every chapter.
**Help** in the side panel, or F1, opens the section of the page you are on.
Under the chapters, **Project on GitHub**, **Releases** and **Report a problem** open the project's pages in your browser.

### Settings

Shared settings kept on this PC, one editor for each (see [Settings](07-settings.md)).
Every page that uses one shows its value with a link back here.

## Explore

### Lot summary

Every opened file as one run of its lot, in test order: good, bad, total and yield, the yield of each site and the parts in each hard or soft bin.
**Columns** picks the MIR fields shown beside them (mode, CMOD, step name, engineering ID, tester, station, program, rev, start and finish by default); Settings, Field names renames them.

- The last row of a lot is its final result after the retests, with the first-pass yield.
- Runs are put in passes: pass 1 is the first run with its continuations, each retest of rejects starts the next pass, and a 100% retest starts the count over.
- What a run is to the lot comes from its CMOD code (T first run, C continuation, F retest of rejects, R 100% retest) or, without one, from RTST_COD. It can be changed per row.
- An engineering run (MODE_COD E) is left out unless you change its row.
- Runs belong to one lot when they share the fields of Settings, Lot recipe: lot, step, flow and program by default.
- A bad part in a bin listed under **Bins not retested** (hard bins 2, 5 and 6 by default) is a final bad part from whichever pass.
  Tick the hard bins of the open runs under **Hard bins**, or type them, with soft bins as `S206`.
- Colour grades the yields and bad bins of pass 1 and of the final result. A later pass is faded, since its yield is not the lot's, and a run left out is grey.

Parts are counted, not matched between files (Part Trace matches them), and the part filter does not apply.
The table downloads as CSV.

### Overview

KPIs, the hard and soft bin pareto, yield by site, wafer and file, a stacked bin map, the fail pareto and the bins.
Click a test in the fail pareto to open it in Test explorer.
With more than one site, **Split the bars by site** shows each site separately.
Instrument alarms and the datalog records (GDR, DTR) are listed with their parts.

### Test explorer

The tests on the left, the charts of one test in the middle and the statistics of each layer on the right.

- The Cpk column is shaded by the Cpk rule (see [Look and themes](06-look.md#shaded-cells-and-rules)); failing tests are red.
- Four chart cards: histogram, trend, box plot and normal probability plot. Each card's type menu switches it to any of these or the CDF; **Expand** fills the middle of the page with one, so the tests and the statistics stay beside it, and it stays expanded when you pick another test.
- Each card's settings button holds its look: bin size, 2D or 3D and depth, and % of layer on a histogram; lines on and off with their width and opacity on a chart of points; the opacity and the axis range. The bin size is the chart's own; the others apply to every chart.
- Type a test number or name in the search box and press Enter to open it. With no exact match, the nearest test by number or name opens and the page says so.
- Drag the inner edge of the test list or the statistics to resize it, or minimize it to a strip with its button; click the strip to bring it back.
- **Compare by** splits the parts into layers: sites by default, or good and bad, bin, wafer, file or loadboard. A layer's tick shows or hides it.
- **Filter by** keeps some parts, on top of the part filter of the side panel: good or bad parts, some hard or soft bins (or all but them), some sites, some part IDs (or all but them), the first or the last test of each part, odd or even parts, parts inside or outside the limits of the test shown, or a filter of your own. The test list follows it, except inside and outside, which change only the charts.
- A second test adds a scatter.
- Right-click a test in the list, or the test's name in Statistics, to copy its number, its name or both. A chart card's **More** menu copies them too.

#### Marked parts

Right-click a point of the trend or the scatter and choose **Mark this part**.
The part is crossed and labelled on every chart of the test, and it stays marked when you pick another test or switch to another file.
A mark keeps the part's wafer, X, Y and part text (Settings, Part identification), so it finds the same physical part in the other files, its retests too; a row must agree on every one of those IDs both files have.
A part with neither stays marked in its own file only.

Statistics lists the marked parts with how many this chart shows.
**Find in files** lists the open files the parts are in and opens one, **Undo** takes back the last change, and **Clear all** unmarks every part.
Right-click a cross to unmark that part, copy its ID or find it in the other files.
Right-click a point or a cross for **Show this part in**: Compare, Part Trace or Part trail open with the part marked; Part Trace looks it up, Part trail opens at its touchdown.
Marks last until the app closes.

A chart of a test opens on the test most parts fail.
The test you pick stays when you switch to another file: the same test number and name, or the same number.
When that file does not have it, the page says so and shows no test, and the test comes back when you switch to a file that has it.

### Compare

Files or groups of files side by side, laid out like Test explorer: every test on the left, the charts of one test in the middle with one layer per entry, and the entries on the right.

- **What is compared**: with two Files groups or more, each group (and each file outside a group); otherwise every file. A group is its lot result when it has one, else its files together.
- A choice in Files takes over: **Compare** on a selection, **Compare with** or **Add to compare** on a file's right-click menu, or a change on this page. **Back to automatic** returns to the groups or files.
- The entries are listed top to bottom as A, B, C… A is the reference. Drag one to reorder; ★ makes it the reference, ⚲ sets a filter of its parts (such as `site = 3`), × leaves it out, **+ Add** adds a file, a group or some parts of the active file. Up to eight entries.
- The test list is sorted by how far a test moved from the reference, with a SHIFT or SPREAD flag (the worst over all entries); **CSV** downloads every test with each entry's mean, shift in sigma and fail %. Type a test and press Enter to open it.
- The four chart cards work as on Test explorer: histogram, trend (each entry's parts one after another), box plot, probability plot or CDF, with settings, Expand and More. Right-click a trend point to mark its part.
- On the right, each entry's statistics of the test, its shift from the reference and its fail %; the tick shows or hides the entry on the charts. Below the charts, the share of each hard bin in every entry.

The part filter of the side panel applies to every entry, together with the entry's own filter.
Ranking marker tests, group against the rest and drift are on [Marker search](#marker-search).

### Wafer maps

A gallery or one wafer, coloured by hard bin, soft bin, pass and fail, or any test value.
Die coordinates come from PRR X/Y and the WIR, or are rebuilt from datalogged tests: wafer, X, Y and X/Y offsets (see [Settings](07-settings.md#die-coordinates-from-tests)).
Flip X and flip Y only turn the map.

### Site map

One value per test site, with the sites placed as they sit on the handler or probe card.
The value is the yield, parts or bad parts, the share or count of a bin, the mean, median, sigma, Cpk or out-of-limit share of a test, or the mean test time.
Bars on top and at the side give the same value for each column and row of sites.
Rates and test values are coloured against the value over all sites, the worse side in the fail colour.

The places follow the file's sites: four sites are placed `1 2` over `4 3`, eight sites `5 1 4 8` over `6 2 3 7`, and other counts in rows from left to right.
**Layout** changes the rows, the columns and the site in each place for the open dataset; it is not saved, so the next file starts from its own sites.

### Part trail

Every part in the order it was tested: a column for each touchdown and a row for each site.
A good part is green, a bad part red, and an empty place means the site tested no part in that touchdown.
Each cell shows the hard bin, soft bin, first or last failing test, part ID, part text, test time or a test value; click a part for its results.
Beside the grid are the yield, the lot and equipment header, bad parts by bin and the site-to-site yield.
Right-click a part to mark it or show it on Test explorer, Compare or Part Trace; marked parts have a ring and a cross.
STDF does not number touchdowns, so they are estimated.

### Part Trace

The same physical parts across files, as charts, a parts table and an Excel report.

- The runs are the files Compare compares (a lot result stands for its group's files), in their order (R1, R2...). Tick or untick a run to choose them yourself; **Follow Compare** goes back.
- **Where the fails went** shows the parts that failed in at least one run, run to run. Click a box to list its parts.
- **Follow test** draws the value of one test in every run.
- Outcomes: recovered, still bad, not retested, never failed. Click one to show only those parts.
- **Parts** lists each part's IDs and a column per run, Run 1, Run 2 and so on, with the part's hard bin in green (pass) or red (fail). Hover a column's name for its file, and a cell for the failing tests, the followed test's value and repeats. The search finds part text, WXY, `W24X111Y146`, `24, 111, 146` or a part ID.
- **Filter runs** keeps the parts that pass, fail, were not tested or got one hard bin in a run: only the rejects of Run 2, say.
- Right-click a part for **Show this part in** Test explorer, Compare or Part trail, with the part marked, or to copy its failing tests. Marked parts are highlighted in the table.

**Part trace report** writes each part's history to an Excel workbook: one row per part and one group of columns per file.
**Identify parts by** picks the IDs; only wafer, X, Y from tests and PRR part text link parts across files, and the others are extra columns.
When they disagree, wafer, X, Y decides, because it is read from the part's own memory.
The **ID audit** lists parts whose IDs disagree, and the workbook has an ID audit sheet and a Summary sheet.

**Find a part**, on this page, looks one part up by any ID.

## Investigate

The pages of Investigate are experimental for now: they are under the **Experimental** switch until they are checked on more real files.

### Kill & catch

Parts that fail a test in a later run (caught), traced back to an earlier run of the same parts: which earlier test could have killed them?

- **Runs**: the earlier run (kill) and the later run (catch). They start on the earliest and the latest file by test time (MIR START_T), of the Files selection when it holds two or more files; ⇄ swaps them.
- **Left**: the later run's tests, the most failed first, and the chart of the catch test, caught parts against the others. The page opens on the test most parts fail; click another test to change it.
- **Right**: the earlier run's tests, ranked by how well they set the caught parts apart from the other parts that link to both runs (rank AUC, the shift in robust sigma, the share beyond 3 sigma, and how many already failed). The best one is shown on the chart, the caught parts' earlier values against the others'; click another test to see it.
- Parts are linked by the ID of **Part identification** (Settings) that links the most parts, of those that name one physical part in every file: wafer, X, Y from tests and part text (part IDs and X/Y restart in every file, so they do not link runs).
- When too few caught parts can be linked, for example because they failed in the later run before the tests that hold their ID, the ranking is a **guess**: the earlier tests that flag about as many parts (failed, alarm, or beyond 4 robust sigma) as were caught. The page says so.
- When no test separates the parts, or none flags about as many, a warning says why and the right side stays as it was.

The part filter of the side panel applies to both runs.

### Drift report

Mean drift of every test on every site, exported to Excel: `ABS(mean1 - mean2) / (USL - LSL)`.
Drift above the threshold (5% by default) is red and Cpk below the minimum (1.33 by default) is yellow.

- **Endurance check** (one looped file): the first 25 loops of each site against its last 25. *Clean* skips failing loops; *Raw* takes them as they are. **Auto trim** leaves out loops at the ends (or also between) until the sites reach the yield threshold. **Save trimmed STDF** writes the compared loops as a new file.
- **25x loop compare** (two files, old and new test program): each site's first or last 25 good loops in each file. Tests pair by number and name, else by number and pin.

The part filter applies; the population does not, because the yield check needs every loop.

## Data & files

### Records

Every STDF record of the dataset by type, paged.
PRR opens as the part table (part text, alarms and first fail, with the part filter applied); click a part for its results and its raw PIR to PRR records.
PTR, MPR, FTR, STR and TSR can be filtered by test number.
Unknown records are listed by type and subtype, such as `UNKNOWN 180/10`, with a hex preview.

### Part datalog

Type a part ID, PRR X/Y (`3,-2`, `W01 3,-2`), a WXY code, wafer, X and Y, or part text, and click a match to add the part; or paste a list.
Give each part a mark and set the order with the arrows.
Pick tests the same way; a test a part lacks prints as N/A.
Save as readable text (one block per part) or CSV.

### Edit, merge & export

Three tabs for writing new files: Edit & trim, Merge, split & export, and Match parts.
The source file is never changed.

### Edit & trim

Every part of one file is listed.
Pick parts by click, Ctrl+click or Shift+click, by typed IDs or rows (`1-3,5,2000-2012`), by rules (filter, result, sites, touchdown) or by a quota (N good parts from each ticked site).
Each pick is previewed and applied with Replace, Add to selection or Take out of selection.
Keep or remove the selection, keep the part IDs or number them 1 to N, and save a new STDF (or save and open it).

### Merge, split & export

- **Merge**: files of the same lot and test step, in the order you set, into one dataset or one merged STDF. Parts the files share are reported. Part IDs can be renumbered to continue from file to file.
- **Export**: an offline HTML report, a CSV, or the filtered parts as a new STDF.
- **Split**: by bin, site, wafer, part ID, part text, a test's value, a pasted list of parts or your own groups.

Save buttons open the Windows save dialog in the last folder used.

### Match parts

Finds the same physical parts in two files by part text, part ID, X/Y, wafer and X/Y, or datalogged tests, and makes a `$name` part set in both.
From there: find marker tests, make matched and unmatched datasets, open Split with the groups filled in, the **dual view** (test X of file A against test Y of file B over the same units), and all results of one matched unit side by side.

## Experimental

These pages are under the Experimental switch.

### Failure investigation

One case for a failure that spans lots: issue lots, clean lots, files to screen, the failing test, the part identity and the loadboard test.
Save the case as JSON and load it back.
Five steps reuse it: the retest and recovery window, bad candidates, commonality across lots, a signature learned from the first issue lot, and a screen of the other files.

### Bad candidates

Parts good in file 1 that are bad in file 2 (optionally failing one test), matched by part text, become `$bad_candidate` in file 1 and are profiled against the other good parts.
A value range for the failing test (in the test's display unit, such as `10..20` mA) keeps only hard fails; fails outside it are `$marginal`.
Good parts that pass file 2 become `$confirmed_good`.
The page ranks focus tests and shows outlier indicators, common factors and a wafer map of the candidate rate.

### Signature check

Learns a failure signature from the bad candidates and screens other files with it.
Each test gets the threshold rule that best separates the candidates from normal parts.
A **reference pool** of good parts (clean lots, parts that stayed good on a 100% retest, confirmed good parts) prunes rules that raise false alarms.
The signature is built step by step and never does worse than its best single rule.
Rules are also shown as part filters, such as `t[1290] > 20.723`.

### Retest recovery

Follows parts through a chain of runs (run 1, a retest of its rejects, and so on), matched by part text by default.
It shows per run how many parts were due, retested, recovered or failed, a Sankey of where run 1's fails went, a trajectory chart and a run-to-run scatter.
The **ID audit** finds IDs shared by different parts and placeholder values.
**Recovery by failing value** finds a hard-bad zone, which **Use as hard-bad range** sends to Bad candidates.

### Correlation

- **Unit correlation**: the same parts on two testers, paired by their IDs. Each test is CORRELATED, OFFSET or UNCORRELATED, with a bin-agreement matrix.
- **Test-to-test**: a Pearson or Spearman matrix with the strongest pairs.
- **Target**: tests ranked by their correlation with fail or with another test.

### ANOVA

One-way ANOVA (F, p, eta squared), Kruskal-Wallis and Brown-Forsythe/Levene for every test, against site, head, wafer, file, bin, X, Y, the loadboard or any test's value.
P-values are corrected with Benjamini-Hochberg.
Click a test for its group means and box plots.

### Abnormal parts

Five detectors combined into one score per part: robust z (median and MAD), static PAT limits, wafer nearest-neighbour residual, Mahalanobis distance and Isolation Forest.
Each part lists its top contributing tests.
An anomaly wafer map, a drill-down per part and **Use as filter** are included.

### Machine learning

PCA with k-means clustering, and a class-balanced random forest that predicts pass and fail, hard bin, soft bin, site or a test value.
It shows feature importance, ROC AUC, a decision threshold tuned on out-of-bag data and a confusion matrix or predicted-versus-actual plot.

### Marker search

Which tests set one population apart from another: file A against file B, or a group of parts against the rest of one file (optionally with drift against a second file of the same units).
**Marker candidates** ranks every test by several signals at once: separation, tails, PAT, ANOVA, drift, correlation break and a random forest. Tick the **Score methods** that count; the ranking follows at once without running again.
Below it: box plots of the top tests, a volcano plot, bin deltas and the full two-way table (mean and median shift in sigma and in % of the limit range, sigma ratio, Welch t-test, Kolmogorov-Smirnov and Benjamini-Hochberg q-values).
