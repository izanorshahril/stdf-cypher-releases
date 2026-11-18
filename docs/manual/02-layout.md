# The window

The window has five parts: the side bar on the left, the banner at the top, the page in the middle, the side panel on the right and the status bar at the bottom.
The banner only names the page and what it shows; the controls are in the side bars.

## Side bar

The side bar lists the pages in groups: Explore, Investigate, Data & files and Experimental.
Click a group heading to fold or unfold it; the app remembers each group.
Home is at the top, and Help and Settings are at the bottom.

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

The banner names the page and its open tab, and shows what the page uses, without controls of its own:

- the **active dataset**, the one the pages work on. It is picked in Files; click its name to show it there, and rename it from its right-click menu;
- the **parts**: all parts, or good parts only;
- the **part filter**, when there is one. Click it to edit it in the side panel.

## Search

Ctrl+K, or **Search** at the top of the side panel (the magnifier on its rail), finds:

- pages and tabs;
- tests of the dataset, with their Cpk (a test opens in Test explorer);
- recent filters, to apply again;
- actions, such as switching light and dark or hiding the side panel;
- sections of this manual.

Use the arrow keys and Enter, or click a result.

## Side panel

The side panel on the right starts with what every page uses:

- **Search** (Ctrl+K) and **Help**, which opens this manual at the page you are on (F1 does the same);
- **Parts**: all parts, or good parts only;
- **Part filter** (see [Part filter](05-filters.md)): Apply, or press Enter, to use it; Shift+Enter starts a new line; Clear removes it.

Under them are small widgets:

- **Chipper** (experimental): a helper that shows facts about the data, tips about the app and sections of this manual (**Read more** opens them), and answers a typed question about pages, tests and facts.
- **Insights**: ranked facts about the parts in scope, each from a fixed rule with its number: yield, top fail bin, most frequent first fail, a site or wafer at least 2 points under the rest, and tests under the Cpk warning threshold. Each has a button to the page that shows more and, where it fits, **Filter to these**.
- **Recent filters**: the last ten filters, to apply again in one click.

The arrow at the bottom collapses the panel to a thin rail with icons for search, help and the part filter, then one per widget; click one, or the rail, to open it again.
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
- **Lines** between the points of a chart of parts (a trend, a scatter, a trajectory): **Show** or **Hide**, with their width and opacity. Until you pick, a trajectory has its lines and a trend does not.

## Chart cards

On Test explorer and Compare each chart is a card with a small header:

- its **type menu**, to show the same data another way (a histogram as a box plot, a CDF or a trend, say), at once and without a new calculation;
- **Settings** (the gear): the chart's look, see below;
- **Expand** (⤢), so the chart fills the page, or on Test explorer the space between the tests and the statistics; Escape or the button again puts it back;
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
