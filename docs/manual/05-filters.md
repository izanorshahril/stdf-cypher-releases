# Part filter

One expression language picks parts everywhere: in the banner's filter box, on pages that take a filter, and in the `-f` option of the commands.
The filter in the banner applies to every page and export, and the status bar shows it.

## Syntax

| What | Example |
|---|---|
| Fields | `part_id file head site x y xy hbin sbin pass fail wafer lot sublot num_test test_t part_txt index retest alarm inst_alarm first_fail n_fails loadboard site_loadboard` |
| Test values | `t[1000]` (test number), `t["VDD_LEAK"]` (name), `t["1000:VDD_LEAK"]` (key) |
| Comparison | `=  ==  !=  <  <=  >  >=` |
| Sets and ranges | `hbin in (2, 5..9)`, `site not in (3)`, `t[1000] between 0.1 and 0.4` |
| Regular expressions | `wafer ~ "W0[1-3]$"`, `part_txt !~ "RETEST"` |
| List file | `part_id in @ids.txt` (one value per line, `#` comments allowed) |
| Logic | `and or not ( )`, also `&& \|\| !` |
| Flags | bare `pass`, `fail`, `retest`, `alarm` (a test with the TEST_FLG alarm bit), `inst_alarm` (an instrument alarm in a GDR or DTR) |
| Failed tests | `fail(1013)`, `fail(1013, 1020)`, `first_fail = 1013`, `fail(1013) and n_fails = 1` |
| Part sets | `$match`, `not $match and pass` (sets made by Match parts, Bad candidates and the other pages) |

A test fails when its TEST_FLG fail bit is set or its value is outside the limits.

## Examples

| Filter | Parts |
|---|---|
| `site in (1,2) and hbin != 5` | sites 1 and 2, except hard bin 5 |
| `not pass and wafer ~ "W0[1-3]"` | bad parts of wafers W01 to W03 |
| `t[1000] > 0.35` | test 1000 above 0.35 |
| `fail(1013) and n_fails = 1` | parts that failed only test 1013 |
| `part_id in (1..100)` | part IDs 1 to 100 |
| `loadboard = 2` | parts tested on loadboard 2 |
| `$bad_candidate` | the bad candidates found on Bad candidates |

## Tips

- Wafer, X and Y from tests are written as one ID with letters, `W12X-2Y25`, because `|` reads as "or".
- The Scope widget in the side panel and the search keep the last ten filters.
- **Filter to these** on an Insight, and **Use as filter** on Abnormal parts, write the filter for you.
- A filter with a mistake makes the page show the error in its place; correct it, or click Clear.
