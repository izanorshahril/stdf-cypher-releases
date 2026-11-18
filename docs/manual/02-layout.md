# The window

The window has five parts: the side bar on the left, the banner at the top, the page in the middle, the side panel on the right and the status bar at the bottom.

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

The banner names the page and its open tab, and holds what every page uses:

- **Dataset**: the files the pages work on. The pencil button renames it.
- **Parts**: all parts, or good parts only.
- **Filter**: the part filter (see [Part filter](05-filters.md)). Apply or press Enter to use it; Clear removes it.
- **Search** (Ctrl+K).
- **?** opens this manual at the page you are on (F1 does the same).

## Search

Ctrl+K, or the search button, finds:

- pages and tabs;
- tests of the dataset, with their Cpk (a test opens in Test explorer);
- recent filters, to apply again;
- actions, such as switching light and dark or hiding the side panel;
- sections of this manual.

Use the arrow keys and Enter, or click a result.

## Side panel

The side panel on the right holds small widgets:

- **Chipper** (experimental): a helper that shows facts about the data, tips about the app and sections of this manual (**Read more** opens them), and answers a typed question about pages, tests and facts.
- **Insights**: ranked facts about the parts in scope, each from a fixed rule with its number: yield, top fail bin, most frequent first fail, a site or wafer at least 2 points under the rest, and tests under the Cpk warning threshold. Each has a button to the page that shows more and, where it fits, **Filter to these**.
- **Scope**: the dataset, population and filter, with the last ten filters to apply again.

The arrow at the bottom collapses the panel to a thin rail; click the rail or a widget icon to open it again.
On narrow windows the panel floats above the page; click outside it or press Escape to close it.

## Status bar

The status bar lists what is open: STDF files, parts, tests, size on disk, lots and test steps, and the filter in use.

At the right, the resource monitor shows the CPU, memory and GPU the app uses, and the free share of the disk.
Hover, focus or click a chip for system figures and app storage.
A chip turns amber when the PC's free share of that resource falls under its limit (5% by default, set in Settings, Charts and status bar).
Resource counters work on Windows; other systems show `n/a`.

## Right-click menus

A right click anywhere offers: open files, switch dataset, go to any page or tab, search, refresh, the side bar and panel switches, light or dark, and the theme.
On a chart it adds **Reset zoom** and **Save chart as PNG**.
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
