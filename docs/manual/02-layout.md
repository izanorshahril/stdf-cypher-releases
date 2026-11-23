# The window

The window has five parts: the side bar on the left, the banner at the top, the page in the middle, the side panel on the right and the status bar at the bottom.
The banner only names the page and its tab; the active dataset and the filters in use are at the top of the side panel.

## Side bar

The side bar lists the pages in groups: Explore, Investigate, Data and Experimental.
Click a group heading to fold or unfold it; the app remembers each group.
The **File** list under Home stays at the top while the pages under it scroll; it takes at most half the window's height and scrolls its files on its own. Fold it to free the room.
Home is at the top, with the version on the same line: click the version to check for a new one. It shines with a dot while a newer version is out.
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
**+ Filter** offers good parts only (or all parts again), bad parts, parts with an alarm, sites, hard bins, soft bins, the first test of each part, or a custom filter in the [filter language](05-filters.md); it adds to the filters already in use.
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
- **Legend** of a chart that compares layers (sites, files, groups; not the box plot): **Right** or **Left** over the plot, **Below** the axis, or **Off**. It is kept when you copy or save the chart.
  With more than eight files or groups, Right and Left leave the legend out, since it would cover the plot; the statistics beside the charts name each one, and Below still shows it.
  Past eight layers the colours repeat, so layers 9 to 16 are drawn with square marks and dotted lines, and 17 to 24 with diamonds and dashes.
  **Legend names**, when the layers are files or groups: shortened (a long file name is cut in the middle), full names, lot and step (from each file's MIR or the lot details set on Home), or Dataset 1, 2, … Sites and bins keep their names.
- **Lines** between the points of a chart of parts (a trend, a scatter, a trajectory): **Show** or **Hide**, with their width and opacity. Until you pick, a trajectory has its lines and a trend does not.

## Chart cards

On Test Explorer and Compare each chart is a card with a small header:

- its **type menu**, to show the same data another way (a histogram as a box plot, a CDF or a trend, say), at once and without a new calculation;
- **Settings** (the gear): the chart's look, see below;
- **Expand** (⤢), so the chart fills the page, or on Test Explorer the space between the tests and the statistics; Escape or the button again puts it back;
- **More** (⋯, or a right click on the header): collapse the card to its title, copy the chart as an image, save it as PNG, or reset the zoom.

The type and the collapsed state of each card are kept for that page. More pages follow.

A card's **Settings** hold what the bar of options holds on other pages, for that chart: on a histogram its bin size, **2D** or **3D** (3D by default, for every histogram at once) and in 3D the **Depth**, how far each layer stands behind the one before it (0 puts them in one plane); on a chart of points its lines; the opacity and the axis range.
The bin size is the chart's own; the other settings apply to every chart.
Other charts are always 2D.
On pages without cards, each histogram has these above it.

The resource monitor at the right of the status bar opens a small window with a card per resource: a bar of this app's share and the whole PC's, a mark at the low limit, and a sparkline of the last two minutes.

## Right-click menus

A right click anywhere offers: open files, switch dataset, go to any page or tab, search, refresh, the side bar and panel switches, light or dark, and the theme.
On a chart it adds **Reset zoom**, **Save chart as PNG** and **Copy chart as image** (also a button in the chart's toolbar), ready to paste into a mail, a chat or a slide.
Files, groups and Chipper have menus of their own.

Shift + right click, or a right click in a text field or on selected text, keeps the browser's own menu.

## Keyboard

| Key | Does |
|---|---|
| Ctrl+O | Open files |
| Ctrl+K | Search |
| F1 | Help for this page |
| Escape | Close a menu, the search, a flyout or the floating side panel |
| Arrow keys | Move in menus, flyouts and the search; resize a focused pane edge |
