# The window

The window has five parts: the side bar on the left, the banner at the top, the page in the middle, the side panel on the right and the status bar at the bottom.
The banner only names the page and its tab; the active dataset and the filters in use are at the top of the side panel.

## Side bar

The side bar lists the pages in groups: Explore, Investigate, Data and Experimental.
Click a group heading to fold or unfold it; the app remembers each group.
The **File** list under Home stays at the top while the pages under it scroll; it takes at most half the window's height and scrolls its files on its own. Fold it to free the room.
Home is at the top, with the version on the same line: click the version to check for a new one. It shines with a dot while a newer version is out.
A narrow sidebar hides the version, then the help button, so the name stays clear of the page; a waiting update keeps the version in place of the help button.
The **?** button at the top right opens this manual at the page you are on (F1 does the same).
Settings is at the bottom.
**Open** under them opens STDF files; right-click it to open a whole folder, or drop files and folders anywhere on the window.

The arrow at the bottom shrinks the side bar to one icon per group.
Hover or click a group icon to open its pages in a flyout; the arrow keys and Escape also work there.

Drag the inner edge to change the width, or focus the edge and use the arrow keys.
Double-click the edge for the default width.
Widths are kept between launches.

### Quick settings

Under the pages are the theme picker, the light and dark switch (the half-circle button) and the **Experimental** box.
The Experimental box turns the experimental pages and themes on or off in one click.
Settings, Experimental features, picks which pages it takes along.

## Banner

The banner names the page and its open tab.

## Search

Ctrl+K, or **Search** at the top of the side panel (the magnifier on its rail), finds:

- pages and tabs;
- tests of the dataset, with their Cpk (a test opens in Test Explorer);
- recent filters, to apply again;
- Chipper's facts about the data in scope, when experimental features are on;
- actions, such as switching light and dark or hiding the side panel;
- sections of this manual.

Use the arrow keys and Enter, or click a result.

## Side panel

The side panel on the right starts with **Search** (Ctrl+K), the one search over pages, tests, actions, the manual and Chipper's facts.

Under it are the **active dataset**, the one single-file pages show (click it to switch to another open dataset, or to show it in File), **+ Filter**, and the **filters in use**, each as a chip.
**+ Filter** offers good parts only (or all parts again), bad parts, parts with an alarm, sites, hard bins, soft bins, the first test of each part, the values of the Loadboard ID and of each other trace field of Settings, or a custom filter in the [filter language](05-filters.md); it adds to the filters already in use.
The chips:

- **Good parts only**, when every page uses good parts only;
- each part of the part filter joined by *and*, said plainly where it is a common one (`site in (1,2)` reads **Sites 1, 2**, `pass` reads **Good parts**); a filter with *or* at its top is one chip, since taking one side out would change the rest;
- the page's own **Filter by** (Test Explorer, Compare), marked *page*.

Click a chip's **×** to take that filter out (it brightens on hover); **Clear all** takes every one out.
With no filter in use there is no chip.
A filter can also come from a page (**Use as filter**, **Filter to these**) or from Search's recent filters; Search also switches good parts only on or off.

Under them are small widgets:

- **Chipper** (experimental): a helper that shows facts about the data, tips about the app and sections of this manual (**Read more** opens them).
  With no files open, Chipper says how to open some, with **Open files** and **Open a folder**.
  Urgent messages come first, marked **CHECK THIS**: a resource under its limit, and wafer, X, Y settings that look wrong for the open data (most parts missing them, empty placeholder values, many parts on few die positions, or a WXY test that disagrees), with a button to Settings.
- **Marked parts**, while a part is marked: each one as a chip. A mark crosses the part on every chart, in every file it is in, and leaves the other parts as they are: it highlights, it does not filter. Click a part's name to show it on another page, **×** to unmark it; **Undo**, **Find in files** and **Clear all** are under them. After the last one goes, the widget stays on that page with **Undo**. Test Explorer and Compare say how many marked parts their chart shows.
  When the marks hold more than one kind of ID (wafer, X, Y and part text, say), **Name by** picks the one each part is named by, on its chip and on the charts, for example CWXY or ULT; a part without that ID keeps its first. Right-click a chip for the same choice, to copy its IDs, find it in the files, show it on another page or unmark it.
- **Insight**: ranked facts about the parts in scope, each from a fixed rule with its number: yield, top fail bin, most frequent first fail, a site or wafer at least 2 points under the rest, and tests under the Cpk warning threshold. Each has a button to the page that shows more and, where it fits, **Filter to these**.

The arrow at the bottom collapses the panel to a thin rail with icons for search and help, the number of filters in use, then one per widget; click one, or the rail, to open it again.
On narrow windows the panel floats above the page; click outside it or press Escape to close it.

## Status bar

The status bar lists what is open: STDF files, parts, tests, size on disk, lots and test steps, and the filter in use.

At the right, the resource monitor shows the CPU, memory and GPU the app uses, and the free share of the disk.
Hover, focus or click a chip for system figures and app storage.
A chip turns amber when the PC's free share of that resource falls under its limit (5% by default, set in Settings, Charts and status bar).
Resource counters work on Windows; other systems show `n/a`.

## Chart options

Pages with charts have a bar of options above them; every chart follows, and the choices are kept.

- **Axis range**: within the limits, the results, or both.
- **Histogram**: % of each group or counts.
- **Opacity** of bars and points.
- **Legend** of a chart that compares layers (sites, files, groups; not the box plot, whose axis names each box): **Right** or **Left** over the plot, **Below** the axis, or **Off**. Each chart keeps its own: a card keeps one for each chart type, so its histogram can have the legend at the left and its probability plot below. Set it in the card's **Settings**, or right-click the legend. It is kept when you copy or save the chart.
  With more than eight files or groups, Right and Left leave the legend out, since it would cover the plot; the statistics beside the charts name each one, and Below still shows it.
  A chart with its own legend in rows above the plot lists more than twelve layers beside the plot instead, scrolling when the list is taller than the chart, so the rows never cover the title.
  Past eight layers the colours repeat, so layers 9 to 16 are drawn with square marks and dotted lines, and 17 to 24 with diamonds and dashes.
  **Legend names**, when the layers are files or groups: shortened (a long file name is cut in the middle), full names, lot and step (from each file's MIR or the lot details set on Home), or Dataset 1, 2, … Sites and bins keep their names. Compare's box plot names its boxes the same way.
- **Lines** between the points of a chart of parts (a trend, a scatter, a trajectory): **Show** or **Hide**, with their width and opacity. Until you pick, a trajectory has its lines and a trend does not.

## Chart cards

On Test Explorer and Compare each chart is a card with a small header:

- its **type menu**, to show the same data another way (a histogram as a box plot, a CDF or a trend, say), at once and without a new calculation;
- **Settings** (the gear): the chart's look, see below;
- **Expand** (⤢), so the chart fills the page, or on Test Explorer the space between the tests and the statistics; Escape or the button again puts it back;
- **More** (⋯, or a right click on the header): collapse the card to its title, copy the chart as an image, save it as PNG, or reset the zoom.

The type and the collapsed state of each card are kept for that page. More pages follow.

### Chart height

On Test Explorer, Compare, Abnormal Test and Overview the charts take the height that puts their first two rows in the window, from where the charts start down to the bottom of the page; they size again when the window or a panel changes.
They are never shorter than 200 px, so a small window scrolls.
Drag the bottom edge of any chart (the short bar that shows on hover) to make every chart of the page taller or shorter at once, or focus the edge and use the up and down arrow keys.
The height you set is kept for that page; a double click on the edge fits the charts to the window again.

A card's **Settings** hold what the bar of options holds on other pages, for that chart: on a histogram its bin size, **2D** or **3D** (3D by default, for every histogram at once) and in 3D the **Depth**, how far each layer stands behind the one before it (0 puts them in one plane); on a chart of points its lines; the opacity and the axis range.
The bin size and the legend are the chart's own; the other settings apply to every chart.
Other charts are always 2D.
On pages without cards, each histogram has these above it.

The resource monitor at the right of the status bar opens a small window with a card per resource: a bar of this app's share and the whole PC's, a mark at the low limit, and a sparkline of the last two minutes.

## Panels

On Test Explorer, Compare and Site Map the boxes around the charts are panels you arrange, as on a dashboard; more pages follow.

- The dock buttons in a panel's head put it on the left, on the right or at the bottom.
- Drag a side's inner edge, or the bottom's top edge, to resize it; a double click gives the default size back.
- **–** in a panel's head minimizes it to its title bar, in its place, and the other panels of its side take the room; a click on the title bar, or **+**, opens it again.
- A side whose panels are all minimized becomes a narrow strip with their titles; a click opens them all.

Where each panel sits, its size and whether it is minimized are kept for each page.

## Tables

Every table works the same way, on every page:

- **CSV** saves the rows shown as a file, and **Copy** puts them on the clipboard to paste into a sheet; the search and the column filters apply, and so do the columns shown.
- A click on a header sorts by that column, again reverses it.
- Drag a header's right edge to make the column wider or narrower; a double click fits it again.
- A right click on a header: **Highlight cells…** frames the cells that pass a rule written as a column filter (`>1.33`, `<=5`, `1..2`, `!text`), **Clear the highlight**, **Fit the width**, and, where the table has a **Columns** menu, **Move left**, **Move right** and **Hide this column**.
- A right click on a row copies the cell, the row, or the test the row is about.
- **Columns** lists the columns shown first, in their order, then the others.
  Tick a column to add it at the end; drag a column's grip (⠿) to move it, or press Alt+Up or Alt+Down on it.
  A header dragged sideways moves its column too; the first column stays first.
  **Default columns** goes back to the page's own.
- A column the rows leave empty is hidden while it is (**Columns** marks it *(empty)*) and shows again when rows fill it.
  Until you pick, a table also shows the alarm columns wherever the data has alarms.

Widths, highlights and the columns' order are kept for each table that keeps its columns.

### Test tables

Every table of tests offers the same common columns under **Columns**, in the same order, around the page's own:

- First the test's facts: **Test order**, **Test #**, **Test name**, **Units**, **Low limit** and **High limit**.
  **Test order** is 1 for the first test the file runs, then 2, and so on, whatever the test numbers, so test 10000 can come before test 6000; sort by it to read the tests in flow order, or filter it (`<100`) for the start of the flow.
  It is where the file first runs each test, so a test only some parts run is placed where it first runs.
- Then the page's own columns.
- Then what the parts selected did on the test: **N**, **Mean**, **Sigma**, **Min**, **Max**, **Median**, **Cpk**, **Fails**, **Fail %**, **HBin**, **SBin**, **Alarms** (the parts whose result carried the tester's alarm flag) and **Instr. alarms** (the instrument alarm records in the datalog that name the test's number).
  They follow the page's filter and the dataset the table is about (each run on Kill & Catch); filter the alarm columns with `>0` for the tests that raised any.
  Compare, which spans several files, offers the facts only.

A page's own column of the same name keeps its own meaning (Abnormal Test's **N** counts the results it compared), and a page column with another meaning (Site Map's **All sites %**) replaces the common one.

## Right-click menus

A right click anywhere offers: open files, switch dataset, go to any page or tab, search, refresh, the side bar and panel switches, light or dark, and the theme.
On a chart it adds **Reset zoom**, **Save chart as PNG** and **Copy chart as image** (also a button in the chart's toolbar), ready to paste into a mail, a chat or a slide.
A click on a legend entry hides or shows that layer and a double click shows it alone, as in any chart; a right click on the legend never hides a layer, it opens the legend's menu: hide or show that layer, show it alone, show all, its **Layer colour** (see Look), or **Move the legend** of this chart (right, left, below or hidden).
Files, groups and Chipper have menus of their own.

Shift + right click, or a right click in a text field or on selected text, keeps the browser's own menu.

## Keyboard

| Key | Does |
|---|---|
| Ctrl+O | Open files |
| Ctrl+K | Search |
| F1 | Help for this page |
| F2 | Rename the file or group in Files, or the active dataset |
| Escape | Close a menu, the search, a flyout or the floating side panel |
| Arrow keys | Move in menus, flyouts and the search; resize a focused pane edge |
