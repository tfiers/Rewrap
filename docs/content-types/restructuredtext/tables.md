# reStructuredText: Tables

> language: "reStructuredText"

No wrapping is attempted on the contents of tables. They are left as-is.

## Grid tables

Grid tables are detected by a line that starts and ends with `+`, with 3 `-` inbetween,
and then a second line with the same indent, that starts with `|`. Lines after that must
start with `|` or `+`, and be at the same indent.

    +---+         ¦                           +---+         ¦
    | a |         ¦                           | a |         ¦
    +---+         ¦                    ->     +---+         ¦
                  ¦                                         ¦
    normal paragraph                          normal        ¦
                  ¦                           paragraph     ¦

An indented grid table (ie: in a blockquote) is fine.

      +---+       ¦                             +---+       ¦
      | a |       ¦                             | a |       ¦
      +---+       ¦                    ->       +---+       ¦
                  ¦                                         ¦
    normal paragraph                          normal        ¦
                  ¦                           paragraph     ¦

Like everything else, grid tables can't interrupt a paragraph at the same indent.
Everything will be treated as normal paragraph text.

    normal paragraph                          normal         ¦
    +---+          ¦                   ->     paragraph +---+¦
    | a |          ¦                          | a | +---+    ¦
    +---+          ¦                                         ¦

At a different indent does work (though may give a warning)

    normal paragraph                          normal        ¦
      +---+       ¦                           paragraph     ¦
      | a |       ¦                    ->       +---+       ¦
      +---+       ¦                             | a |       ¦
                  ¦                             +---+       ¦

      normal paragraph                          normal      ¦
    +---+         ¦                             paragraph   ¦
    | a |         ¦                    ->     +---+         ¦
    +---+         ¦                           | a |         ¦
                  ¦                           +---+         ¦

A table ends as soon as a line is encountered that doesn't start with `|` or `+` or has a
different indent. A normal paragraph *can* therefore come directly after a table (with a
warning).

    +---+         ¦                           +---+         ¦
    | a |         ¦                           | a |         ¦
    +---+         ¦                    ->     +---+         ¦
    normal paragraph                          normal        ¦
                  ¦                           paragraph     ¦

If a line that looks like the start of a table is followed by a line that doesn't continue
the table, the first line is ignored.

    +---+         ¦                           +---+         ¦
    normal paragraph                   ->     normal        ¦
                  ¦                           paragraph     ¦


## Simple tables

Not supported yet.
