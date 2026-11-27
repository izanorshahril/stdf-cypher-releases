# Pages

Every page uses the dataset, the population (all parts or good parts only) and the part filter shown at the top of the side panel, unless it says otherwise.
Raw records, the Datalog, Find a part and Edit & Trim work on the whole file and say so.

A page or tab has its own address, such as `#data/trim`, and old addresses such as `#parttrace` still open their page.
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

### Lot Summary

Every opened file as one run of its lot, in test order: good, bad, total and yield, the yield of each site and the parts in each hard or soft bin.
**Columns** picks the MIR fields shown beside them (mode, CMOD, step name, engineering ID, tester, station, program, rev, start and finish by default); Settings, Field names renames them.

- The last row of a lot is its final result after the retests, with the first-pass yield.
- Runs are put in passes: pass 1 is the first run with its continuations, each retest of rejects starts the next pass, and a 100% retest starts the count over.
- What a run is to the lot comes from its CMOD code (T first run, C continuation, F retest of rejects, R 100% retest) or, without one, from RTST_COD. It can be changed per row.
- An engineering run (MODE_COD E) is left out unless you change its row.
- Runs belong to one lot when they share the fields of Settings, Lot recipe: lot, step, flow and program by default.
- A bad part in a bin listed under **Bins not retested** (hard bins 2, 5 and 6 by default) is a final bad part from whichever pass.
  Tick the hard bins of the open runs under **Hard bins**, or type them, with soft bins as `S206`; **Clear** unticks them all. The default bins apply only until you choose.
- Drag the right edge of a column's heading to change its width; double-click it to fit again. Widths are kept.
- Colour grades the yields and bad bins of pass 1 and of the final result. A later pass is faded, since its yield is not the lot's, and a run left out is grey.

Parts are counted, not matched between files (Part Trace matches them), and the part filter does not apply.
The table downloads as CSV.

### Overview

KPIs, the hard and soft bin pareto, the fail pareto by test, yield by site, wafer and file, a stacked bin map, the fail pareto table and the bins.
Click a test in the fail pareto chart or table to open it in Test Explorer.
Above the charts, **Top** sets how many bins (and tests on the fail pareto chart) to show, largest first; 0 shows every bin.
**Pass bins** shows or hides the pass bins on the bin charts, and **Bins to show** has a tick for each hard and soft bin, with **All** and **None**.
The bin tables keep every bin, and the choice is kept for the next file.
**Split the bars by** shows each group separately: site, CMOD, lot or file, whichever the dataset holds more than one of.
Split by site or CMOD (groups of one population), the bins are counted; split by lot or file (separate populations), they are % of each, so groups of different size share a scale. **Bins as** switches between Count and %, and each kind keeps your choice.
The automatic choice is marked "automatic" in the list: CMOD for a lot result (its runs), lot when the dataset holds several lots, file for other files, and none for one file; pick a site split for one file.
To compare unrelated files on one Overview, merge them (Edit, Merge & Export) or use their group's lot result.
Instrument alarms and the datalog records (GDR, DTR) are listed with their parts.

### Test Explorer

The tests on the left, the charts of one test in the middle and the statistics of each layer on the right.

- The Cpk column is shaded by the Cpk rule (see [Look and themes](06-look.md#shaded-cells-and-rules)); failing tests are red.
- Four chart cards: histogram, trend, box plot and normal probability plot. Each card's type menu switches it to any of these or the CDF; **Expand** fills the middle of the page with one, so the tests and the statistics stay beside it, and it stays expanded when you pick another test.
- Each card's settings button holds its look: bin size, 2D or 3D and depth, and % of layer on a histogram; lines on and off with their width and opacity on a chart of points; the opacity and the axis range. The bin size is the chart's own; the others apply to every chart.
- The test list shows Test, Fail % and HBin by default, and the alarm columns when the file has alarms; **Columns** adds the other common columns of a test table (see [Test tables](02-layout.md#test-tables)), and **Default columns** goes back. HBin and SBin are the bin most of the parts this test failed first went to. Drag a column header's right edge to widen it (double-click to fit). **CSV** saves every test of the list with its statistics.
- The histogram's **%** / **Count** switch in its card header: layers of separate files compare in % of each layer, layers of one population (sites, bins…) by count, unless you switch it; Compare and the other pages that compare runs default to %.
- **Figures** above the layers in Statistics picks what each layer shows: mean, sigma, min / max, median and Cp / Cpk by default; N can be added. A long test name is cut to fit; hover it for the whole name.
- A filter box sits under every column. Numbers take `>1.33`, `<=5`, `!=0` or a range `1..2`; text is contained (`!text` for rows without it). Type a test number or name under Test and press Enter to open it; with no exact match, the nearest test by number or name opens and the page says so.
- The dock buttons in the head of the test list and of Statistics put each on the left, the right or at the bottom. Panels on one side share its height; two at the bottom sit side by side. Drag a side's inner edge (or the bottom's top edge) to resize it, double-click it for the default, or minimize the side to a strip with its button; click the strip to bring it back.
- **Compare by** splits the parts into layers: sites by default, or good and bad, bin, wafer, file or loadboard. A layer's tick shows or hides it.
- **Filter by** keeps some parts, on top of the part filter of the side panel: good or bad parts, some hard or soft bins (or all but them), some sites, some part IDs (or all but them), the first or the last test of each part, odd or even parts, parts inside or outside the limits of the test shown, or a filter of your own. The test list follows it, except inside and outside, which change only the charts.
- A second test adds a scatter.
- Right-click a test in the list, or the test's name in Statistics, to copy its number, its name or both. A chart card's **More** menu copies them too.

#### Marked parts

Right-click a point of the trend or the scatter and choose **Mark this part**.
The part is crossed and labelled on every chart of the test, and it stays marked when you pick another test or switch to another file.
A mark keeps the part's wafer, X, Y and part text (Settings, Part identification), so it finds the same physical part in the other files, its retests too; a row must agree on every one of those IDs both files have.
A part with neither stays marked in its own file only.
A part that has both shows both on its card in Statistics, and a file that has only one of them still finds it.
Marking the same part again from another file keeps one mark and adds the ID that file has.

Statistics lists the marked parts with how many this chart shows.
**Find in files** lists the open files the parts are in and opens one, **Undo** takes back the last change, and **Clear all** unmarks every part.
Right-click a cross to unmark that part, copy its ID or find it in the other files.
The crosses are labelled by one ID, the first in Settings order, or the one picked with **Name by** in the side panel's Marked parts.
Right-click a point or a cross for **Show this part in**: Compare, Part Trace or Part Trail open with the part marked; Part Trace looks it up, Part Trail opens at its touchdown.
Marks last until the app closes.

A chart of a test opens on the test most parts fail.
The test you pick stays when you switch to another file: the same test number and name, or the same number.
When that file does not have it, the page says so and shows no test, and the test comes back when you switch to a file that has it.

### Compare

Files or groups of files side by side, laid out like Test Explorer: every test on the left, the charts of one test in the middle with one layer per entry, and the entries on the right.

- **What is compared**: with two Files groups or more, each group (and each file outside a group); otherwise every file. With groups, **Compare each** switches between each group and each file, to see every file in one view. A group is its lot result when it has one, else its files together. The automatic entries follow the order of the File list.
- **Up to 20 entries.** With more files or groups open, Compare takes the first 20 as File lists them and says so above the charts; a selection of more than 20 compares its first 20, with a note that stays until the entries change.
- With more than eight entries, the cards above the charts show the reference's yield, the lowest and highest yield and the tests that moved; each entry's yield is listed beside it on the right.
- **Filter by** works as on Test Explorer, on every entry's parts; the test list, its columns and filters and the dock buttons work as there too (Columns adds Test #, Test name, Flag, Most σ and Fail % D1).
- A choice in Files takes over: **Compare** on a selection, **Compare with** or **Add to compare** on a file's or group's right-click menu, a file or group dragged onto this page, or a change on this page. **Remove from compare** on the same menu takes one out again; with fewer than two left, Compare goes back to automatic. **Back to automatic** returns to the groups or files.
- When tests matched as one differ in kind of result (parametric, multi-pin, functional) or in units, a warning above the charts counts them and the test list marks them ≠: their shifts compare unlike values, most often because the files come from different test programs. The warning also names each entry's test program when they differ.
- The entries are listed top to bottom as D1, D2, D3…, or D01, D02… with ten entries or more; D1 is the reference. Hover one for its up and down arrows, or drag it onto the top or bottom half of another (a line shows where it goes); with the keyboard, focus an entry and press Alt+Up or Alt+Down. ★ makes it the reference, × leaves it out, **+ Add** adds a file or a group not compared yet.
- The test list is sorted by how far a test moved from the reference, with a SHIFT or SPREAD flag (the worst over all entries); **CSV** downloads every test with each entry's mean, shift in sigma and fail %. Type a test and press Enter to open it.
- The four chart cards work as on Test Explorer: histogram, trend (each entry's parts one after another), box plot, probability plot or CDF, with settings, Expand and More. Right-click a trend point to mark its part.
- The box plot labels each box by its tag (D1, D01…) over its name, as the legends name it (the card's Settings, **Box names**), and names one statistic at a time, the one nearest the pointer, with the entry's full name (min, lower fence, q1, median, mean ± σ, q3, upper fence, max); the statistics on the right list them all.
- On the right, each entry's statistics of the test, its shift from the reference and its fail %; the tick shows or hides the entry on the charts.

The filters of the side panel and Filter by apply to every entry alike; an entry has no filter of its own.
Ranking marker tests, group against the rest and drift are on [Marker Search](#marker-search).

### Wafer Map

A gallery or one wafer, coloured by hard bin, soft bin, pass and fail, or any test value.
Die coordinates come from PRR X/Y and the WIR, or are rebuilt from datalogged tests: wafer, X, Y and X/Y offsets (see [Settings](07-settings.md#die-coordinates-from-tests)).
Flip X and flip Y only turn the map.

### Site Map

One value per test site, with the sites placed as they sit on the handler or probe card.
The value is the yield, parts or bad parts, the share or count of a bin, the mean, median, sigma, Cpk or out-of-limit share of a test, or the mean test time.
Bars on top and at the side give the same value for each column and row of sites.
Rates and test values are coloured against the value over all sites, the worse side in the fail colour.

The places follow the file's sites: four sites are placed `1 2` over `4 3`; eight, twelve or sixteen in two rows from the middle out, sixteen as `13 9 5 1 4 8 12 16` over `14 10 6 2 3 7 11 15`; other counts in rows from left to right.
A site between the file's sites that tested no part, such as sites 5 and 6 blocked on a 16-site run, keeps its place and is shown as blocked.
**Layout** changes the rows, the columns and the site in each place for the open dataset; it is not saved, so the next file starts from its own sites.
The layout settings and the values are panels: dock them left, right or at the bottom, resize them, or minimise one to its title for a wider map; a click on the title opens it again.
**By site**, under the map, lists the bins or the tests with a column for each site: the share of the site's parts in the bin or outside the test's limits, or the parts (**%** or **Parts**).
It has a filter under each column and a Columns menu; click a bin or a test to show it on the map.
With more than eight sites the site columns are named short: S1 to S8, or S01, S02… when a site number has two digits.

### Part Trail

Every part in the order it was tested: a column for each touchdown and a row for each site.
A good part is green, a bad part red, and an empty place means the site tested no part in that touchdown.
Each cell shows the hard bin, soft bin, first or last failing test, part ID, part text, test time or a test value; click a part for its results.
Beside the grid are the yield, the lot and equipment header, bad parts by bin and the site-to-site yield.
Right-click a part to mark it or show it on Test Explorer, Compare or Part Trace; marked parts have a ring and a cross.
STDF does not number touchdowns, so they are estimated.

### Part Trace

The same physical parts across files, as charts, a parts table and an Excel report.

- The runs are the files Compare compares (a lot result stands for its group's files), in their order (R1, R2…, or R01, R02… with ten runs or more). Tick or untick a run to choose them yourself; **Follow Compare** goes back.
  A file taken out of Compare leaves the runs at once, and right-clicking a run's column in Parts offers **Remove** (out of Compare too while the runs follow it).
- **Follow test** draws the value of one test in every run.
- Outcomes: recovered, still bad, not retested, never failed. Click one to show only those parts.
- **Parts** lists each part's IDs, its outcome and a column per run, R1, R2 and so on, with the part's hard bin in green (pass) or red (fail). Hover a column's name for its file, and a cell for the failing tests, the followed test's value and repeats. The search finds part text, WXY, `W24X111Y146`, `24, 111, 146` or a part ID.
- **Export to Excel**, beside the search of Parts, writes the part trace report (below).
- A filter under each column of Parts narrows the table: text for the IDs, the outcome, and for each run pass, fail, not tested or one hard bin: only the rejects of R2, say.
- **Show** lists the parts that failed in a run or all parts, and, while a part is marked, only the marked parts.
- Right-click a part, or a point of the trajectory chart, for **Mark this part**: it is crossed on every chart of every page, in every file it is in, listed in the side panel's Marked parts, and highlighted in the table. A marked part's menu has **Unmark**; a part's card has **Mark** too.
- The same menu has **Show this part in** Test Explorer, Compare or Part Trail, on the followed test, with the part marked, and copies its failing tests.
- **Where the fails went** (experimental, at the bottom, shown only with experimental features on) draws the parts that failed in at least one run as a flow from run to run. Click a box to list its parts in Parts above.

**Part trace report** (**Export to Excel** on Parts) writes each part's history to an Excel workbook: one row per part with its IDs and its outcome (never failed, recovered, still bad, not retested, by the same rule as the page), and one group of columns per file: part ID, hard bin, site, first and last failing test, and, titled **Value of** the test, the result of a test you typed in **Follow test**.
The test Part Trace opens on by itself is not exported: the report stays at five columns per file.
It holds every traced part of the ticked runs, whatever the table shows.
**Identify parts by** picks the IDs; only wafer, X, Y from tests and PRR part text link parts across files, and the others are extra columns.
When they disagree, wafer, X, Y decides, because it is read from the part's own memory.
**Notes on the IDs**, folded under the runs, gathers what needs a look: repeated tests of a part, IDs that disagree or sit on several parts, the **ID audit** and the shared parts of each pair of files; its line shows a badge for each, and a click opens it.
The workbook has an ID audit sheet and a Summary sheet.

**Find a part**, on this page, looks one part up by any ID.

## Investigate

The pages of Investigate are experimental for now: they are under the **Experimental** switch until they are checked on more real files.

### Kill & Catch

Parts that fail a test in a later run (caught), traced back to an earlier run of the same parts: which earlier test could have killed them?

- **Runs**: the earlier run (kill) and the later run (catch). They start on the earliest and the latest file by test time (MIR START_T), of the Files selection when it holds two or more files; ⇄ swaps them.
- **Left**: the later run's tests, the most failed first, and the chart of the catch test, caught parts against the others. The page opens on the test most parts fail; click another test to change it.
- **Right**: the earlier run's tests, ranked by how well they set the caught parts apart from the other parts that link to both runs (rank AUC, the shift in robust sigma, the share beyond 3 sigma, and how many already failed). The best one is shown on the chart, the caught parts' earlier values against the others'; click another test to see it.
- Parts are linked by the ID of **Part identification** (Settings) that links the most parts, of those that name one physical part in every file: wafer, X, Y from tests and part text (part IDs and X/Y restart in every file, so they do not link runs).
- When too few caught parts can be linked, for example because they failed in the later run before the tests that hold their ID, the ranking is a **guess**: the earlier tests that flag about as many parts (failed, alarm, or beyond 4 robust sigma) as were caught. The page says so.
- When no test separates the parts, or none flags about as many, a warning says why and the right side stays as it was.

The part filter of the side panel applies to both runs.

### Drift Report

Mean drift of every test on every site, exported to Excel: `ABS(mean1 - mean2) / (USL - LSL)`.
Drift above the threshold (5% by default) is red and Cpk below the minimum (1.33 by default) is yellow.

- **Endurance check** (one looped file): the first 25 loops of each site against its last 25. *Clean* skips failing loops; *Raw* takes them as they are. **Auto trim** leaves out loops at the ends (or also between) until the sites reach the yield threshold. **Save trimmed STDF** writes the compared loops as a new file.
- **25x loop compare** (two files, old and new test program): each site's first or last 25 good loops in each file. Tests pair by number and name, else by number and pin.

The part filter applies; the population does not, because the yield check needs every loop.

## Data

### Records

Every STDF record of the dataset by type, paged.
PRR opens as the part table (part text, alarms and first fail, with the part filter applied); click a part for its results and its raw PIR to PRR records.
PTR, MPR, FTR, STR and TSR can be filtered by test number.
Unknown records are listed by type and subtype, such as `UNKNOWN 180/10`, with a hex preview.

### Datalog

The results of the parts and tests you pick, with their limits, as text or CSV; a page of its own under Data.
Type a part ID, PRR X/Y (`3,-2`, `W01 3,-2`), a WXY code, wafer, X and Y, or part text, and click a match to add the part; or paste a list.
While parts are marked, **Marked parts** lists them: click one to add it, or **Add all marked** for every marked part in this file (each test of it).
Give each part a mark and set the order with the arrows.
Pick tests the same way; a test a part lacks prints as N/A.
Save as readable text (one block per part) or CSV.

### Edit, Merge & Export

Three tabs for writing new files: Edit & Trim, Merge, Split & Export, and Match Part.
The source file is never changed.

### Edit & Trim

Every part of one file is listed.
Pick parts by click, Ctrl+click or Shift+click, by typed IDs or rows (`1-3,5,2000-2012`), by rules (filter, result, sites, touchdown) or by a quota (N good parts from each ticked site).
Each pick is previewed and applied with Replace, Add to selection or Take out of selection.
Keep or remove the selection, keep the part IDs or number them 1 to N, and save a new STDF (or save and open it).

### Merge, Split & Export

- **Merge**: files of the same lot and test step, in the order you set, into one dataset or one merged STDF. Parts the files share are reported. Part IDs can be renumbered to continue from file to file.
- **Export**: an offline HTML report, a CSV, or the filtered parts as a new STDF.
- **Split**: by bin, site, wafer, part ID, part text, a test's value, a pasted list of parts or your own groups.

Save buttons open the Windows save dialog in the last folder used.

### Match Part

Finds the same physical parts in two files by part text, part ID, X/Y, wafer and X/Y, or datalogged tests, and makes a `$name` part set in both.
From there: find marker tests, make matched and unmatched datasets, open Split with the groups filled in, the **dual view** (test X of file A against test Y of file B over the same units), and all results of one matched unit side by side.

## Experimental

These pages are under the Experimental switch.

### Failure Investigation

One case for a failure that spans lots: issue lots, clean lots, files to screen, the failing test, the part identity and the loadboard test.
Save the case as JSON and load it back.
Five steps reuse it: the retest and recovery window, bad candidates, commonality across lots, a signature learned from the first issue lot, and a screen of the other files.

### Bad Candidate

Parts good in file 1 that are bad in file 2 (optionally failing one test), matched by part text, become `$bad_candidate` in file 1 and are profiled against the other good parts.
A value range for the failing test (in the test's display unit, such as `10..20` mA) keeps only hard fails; fails outside it are `$marginal`.
Good parts that pass file 2 become `$confirmed_good`.
The page ranks focus tests and shows outlier indicators, common factors and a wafer map of the candidate rate.

### Signature Check

Learns a failure signature from the bad candidates and screens other files with it.
Each test gets the threshold rule that best separates the candidates from normal parts.
A **reference pool** of good parts (clean lots, parts that stayed good on a 100% retest, confirmed good parts) prunes rules that raise false alarms.
The signature is built step by step and never does worse than its best single rule.
Rules are also shown as part filters, such as `t[1290] > 20.723`.

### Retest Recovery

Follows parts through a chain of runs (R1, a retest of its rejects, and so on; R01, R02… with ten runs or more), matched by part text by default.
It shows per run how many parts were due, retested, recovered or failed, a Sankey of where run 1's fails went, a trajectory chart and a run-to-run scatter.
The **ID audit** finds IDs shared by different parts and placeholder values.
**Recovery by failing value** finds a hard-bad zone, which **Use as hard-bad range** sends to Bad Candidate.

### Correlation

- **Unit correlation**: the same parts on two testers, paired by their IDs. Each test is CORRELATED, OFFSET or UNCORRELATED, with a bin-agreement matrix.
- **Test-to-test**: a Pearson or Spearman matrix with the strongest pairs.
- **Target**: tests ranked by their correlation with fail or with another test.

### ANOVA

One-way ANOVA (F, p, eta squared), Kruskal-Wallis and Brown-Forsythe/Levene for every test, against site, head, wafer, file, bin, X, Y, the loadboard or any test's value.
P-values are corrected with Benjamini-Hochberg.
Click a test for its group means and box plots.

### Abnormal Test

The tests where one part reads off from the other parts, or one site from the other sites, also in a file of a few parts.

- **A part** is held against the other parts of its site, or of the whole file when its site has fewer parts than **Parts a site needs** (5 by default): its distance from their median, in their sigma.
  Each part is left out of what it is measured against, so in a file of six parts the odd one does not hide itself.
  **Part σ** is that distance made fair across file sizes: with few parts to go by it counts for less (a Student t prediction), and among many parts the largest by chance is not off (the chance is scaled by the number of parts of the test, also when each part is read against its own site, so more sites do not mean more flags).
  Among many parts, the sigma is that of the bulk of them, so a few far parts (opens, shorts) do not widen it and hide themselves.
  So 2.5 means about the same in a file of six as in one of thousands; plain parts flag a test about once in a hundred.
- **A site** is held against the other sites: its median's shift from the median of the other sites' medians, in the sigma within a site; **Spread ×** shows when a site spreads more than the others.
- A part is off past **Part off at, σ** (2.5 by default), a site past **Site off at, σ** (1.5), and both only when the gap is at least **Least gap, % of limits** (1%) of the limit range, so a tight test does not flag a wobble no one would see.
  A test without both limits takes the gap as a % of its median, or of the spread of its values when the median is 0.

**Within the limits only** (on by default) takes only the results inside the limits that apply to each part, so the page finds passing parts that read a bit off rather than the parts the tester already failed; turn it off to see every result.
The tests list shows, for each test, the **Odd part ID** and **Its site**, and the **Odd site**; filter **Its site** with `=7` for the tests whose odd part is on site 7.
It puts flagged tests first (**Flag**: PART, SITE or both) and shows only those at first; its filter under Flag shows them all.
Click a test for its parts by site: two chart cards, the trend with the parts off ringed and the box plot of each site; each card's type menu shows the histogram, probability plot or CDF instead.
Marked parts are crossed on both charts, and a right click on a point, or on a ringed part, marks it, so it is crossed on Test Explorer, Compare and the other pages too.

### Abnormal Part

Five detectors combined into one score per part: robust z (median and MAD), static PAT limits, wafer nearest-neighbour residual, Mahalanobis distance and Isolation Forest.
Each part lists its top contributing tests.
An anomaly wafer map, a drill-down per part and **Use as filter** are included.

### Machine Learning

PCA with k-means clustering, and a class-balanced random forest that predicts pass and fail, hard bin, soft bin, site or a test value.
It shows feature importance, ROC AUC, a decision threshold tuned on out-of-bag data and a confusion matrix or predicted-versus-actual plot.

### Marker Search

Which tests set one population apart from another: file A against file B, or a group of parts against the rest of one file (optionally with drift against a second file of the same units).
**Marker candidates** ranks every test by several signals at once: separation, tails, PAT, ANOVA, drift, correlation break and a random forest. Tick the **Score methods** that count; the ranking follows at once without running again.
Below it: box plots of the top tests, a volcano plot, bin deltas and the full two-way table (mean and median shift in sigma and in % of the limit range, sigma ratio, Welch t-test, Kolmogorov-Smirnov and Benjamini-Hochberg q-values).
