# Settings

Settings are kept on this PC in `%APPDATA%\stdf-cypher` and shared by every window.
Each page that uses a setting shows its value with a link back here.

## Opening files

The number of threads for loading several files and for reading one file (0 is one per core, the default).
The `--threads` option and the `STDF_CYPHER_THREADS` variable set the same thing for the commands.

**Build the lot result of a file group that follows the recipe** (on by default) adds a group's lot result by itself (see [Files and datasets](03-files.md#lot-results)).

## Part identification

One ordered list of the ways to find a part:

1. wafer, X and Y from tests (default tests `80100`, `80101`, `80102`);
2. PRR part text (ULT);
3. PRR wafer and X/Y;
4. PRR X/Y;
5. the WXY test (default `80149`);
6. PRR part ID.

The first one a file has is the default on pages that match by one ID.
Change the order with the arrows; the test numbers are set in the list.
A checkbox keeps the identification tests out of rankings, signatures and first-fail picks.

The WXY test is checked against the raw wafer, X and Y tests, or against die X and Y when **Check WXY against** is set to die.
Its digits read as wafer, then X and Y padded to three digits: `17113138` is wafer 17, X 113, Y 138.

Each page keeps its own choice of ID, and each ID in a picker shows how many parts of the file have it.

## Labels

How wafer, X, Y and a test are written on every page, in the Excel reports and in CSV files.
Fill in what goes before, between and after each field, or type the template directly with `{w}`, `{x}`, `{y}`, `{num}` and `{name}`.
A check under it says what is wrong, and examples show the result and whether it reads back.
An empty template is the default.

## Die coordinates from tests

The X and Y offset tests (defaults `80103` and `80104`) added to the X and Y tests rebuild die X and Y for Wafer maps, Bad candidates and the Part datalog.
The offset can also be subtracted, and flip X and flip Y turn the map.
They change how parts are identified only when **Check WXY against** is die X/Y.

## Other trace fields

The test program revision, the loadboard test (default `5100`) and any other IDs you add.
Untick **trace** for a test a program does not log; it is then left out of tracing only.

The loadboard is read per file (the most common value), so parts missing it take their file's board, and a file whose board changes is flagged.
It is the filter field `loadboard`, and a factor in colour-by, ANOVA and Bad candidates.

## Experiments

Touchdown and loop per part, estimated from the file (off by default).
Touchdown numbers start at 1 or 0, and loops are counted by part ID, part text, whichever repeats more, or not at all.
Records then shows a touchdown summary and two columns, and Edit & trim can select by touchdown.
The estimate is not validated on real tester files.

## Pages

Every page and tab with a tick box; untick one you do not use and it leaves the side bar.

## Experimental features

Which experimental pages and themes the **Experimental** box in the side bar takes along.

## Look

Theme, mode, type, accent, effects, chart colours, gradients and shaded cells (see [Look and themes](06-look.md)).

## Charts and status bar

- **Axis range** of charts: within limits, results, or both (adaptive).
- **Histogram**: the default histogram scale. Each histogram also has its own bin-size slider.
- **Show resource monitor in the status bar**. Hiding it also stops its sampling.
- **Warn when free falls under**: the low limit for CPU, memory, GPU and disk (5% by default).

**Reset to defaults**, at the bottom of the page, resets every setting on it.
