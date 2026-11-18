# Command line

Run from a terminal, `stdf-cypher.exe` is a normal command-line tool; `stdf-cypher --help` lists the commands and `stdf-cypher <command> --help` the options of one.
With no command it opens the desktop app, the same as a double-click.

```
stdf-cypher lot1.stdf lot2.stdf.gz          # desktop app with these files open
stdf-cypher report lot1.stdf lot2.stdf -o r.html --offline
stdf-cypher compare lot1.stdf lot2.stdf
stdf-cypher split lot1.stdf --by hbin -o out/
```

## Options of every analysis command

| Option | Does |
|---|---|
| `-f`, `--filter EXPR` | Only the parts matching a [part filter](05-filters.md) |
| `--dedup first\|last` | Keep the first or last test of a retested part |
| `--no-ftr`, `--no-mpr` | Skip FTR or MPR records |
| `--threads N` | Threads for loading (0 is one per core) |
| `-o FILE` | For commands that print a table: write the full table as CSV instead of the top rows |

## Commands

| Command | Does |
|---|---|
| `app [FILES...]` | The desktop app |
| `serve [FILES...] [--port 8765] [--merge] [--no-open]` | The dashboard as a local web server |
| `info FILES... [--json]` | MIR, record counts, yield, bins, yield by site and wafer |
| `dump FILE [--rec PRR,PTR] [-n N]` | Records as JSON lines |
| `xlsx FILE -o out.xlsx` | Every record in an Excel workbook, one sheet per record kind |
| `prr FILES...` | The part table, with the first failing test |
| `tests FILES...` | N, mean, sigma, min, max, Cpk and fails per test |
| `export FILES... -o out.csv [--tests 1000,1010]` | A parts by tests matrix |
| `split FILE --by FIELD -o DIR` | One STDF per value of a part field |
| `split FILE -g NAME=EXPR... [--rest NAME] -o DIR` | One STDF per named group (first match wins) |
| `extract FILE -f EXPR -o out.stdf` | The matching parts as a new STDF |
| `trim FILE (--keep SPEC \| --remove SPEC) [--by id\|row] [--renumber] -o out.stdf` | Keep or remove parts by ID or row (`1-3,5,2000-2012`) |
| `compare A B [--match-by key\|num\|name] [--html r.html]` | File A against file B |
| `group FILES... -s EXPR [--vs EXPR]` | A group of parts against the rest |
| `correlate FILE --with FILE2` | Tester-to-tester correlation of the same parts |
| `correlate FILE [--method spearman] [--threshold 0.8]` | Test-to-test correlation |
| `correlate FILE --target pass\|TEST` | Drivers of fail or of a test |
| `anova FILES... --factor site\|head\|wafer\|file\|hbin\|x\|y` | ANOVA, Kruskal-Wallis and Levene |
| `anomaly FILES... [--only-passing]` | Abnormal-part screening |
| `ml pca FILES... [--clusters K]` | PCA and k-means |
| `ml explain FILES... --target pass\|hbin\|sbin\|site\|TEST` | Random-forest drivers |
| `report FILES... -o report.html [--offline] [--title T]` | An interactive HTML report in one file; with `--offline` it carries its chart library and opens without internet, otherwise the page loads the library from a public CDN |
| `part-trace FILES... -o out.xlsx` | Each part's history across files in Excel |
| `endurance FILE -o out.xlsx` | Endurance check of a looped file |
| `loop-compare OLD NEW -o out.xlsx` | 25x loop compare of an old and a new test program |
| `synthetic-sample OUT` | A made-up STDF file for demos and tests |

## Examples

```
# one file per part ID, only parts 1 to 100
stdf-cypher split ft.stdf --by part_id -f "part_id in (1..100)" -o parts/

# named groups; everything else goes to "other"
stdf-cypher split lot.stdf -g "site12=site in (1,2)" -g "fails=not pass" --rest other -o out/

# keep parts 1-3, 5 and 2000-2012 and number them 1 to N
stdf-cypher trim lot.stdf --keep 1-3,5,2000-2012 --renumber -o lot_trim.stdf

# golden units listed in a text file
stdf-cypher extract lot.stdf -f "part_id in @golden_ids.txt" -o golden.stdf

# is site 3 different from the other sites?
stdf-cypher group lot.stdf -s "site = 3"

# passing parts that are outliers
stdf-cypher anomaly lot.stdf --only-passing -o suspects.csv

# synthetic data: a lot, a shifted lot and the same lot on a second tester
stdf-cypher synthetic-sample lotA.stdf
stdf-cypher synthetic-sample lotB.stdf --lot SYNTH_B --seed 2 --shift 0.6
stdf-cypher synthetic-sample lotA_t2.stdf --meas-noise 0.3 --tester-offset 1.5
```

Splitting, extracting and trimming copy records byte for byte, regenerate the bin and part summaries, and never change the source file.
