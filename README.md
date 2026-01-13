# Custom Typst snippets for use in Sublime Text

Typesetting documents, letters, reports, or even books in [Typst] is not as verbose as LaTeX, but certainly error-prone, given the need for strict syntax. A handful of [Sublime Text][st] snippets provided in this repository try to reduce this tedium to as low as practicable.

This repository contains the following custom snippets:

| Snippet                   | Inserts                   |
| ------------------------- | --------------------------|
| `apdx` + <kbd>tab</kbd>   | appendix block            |
| `bib` + <kbd>tab</kbd>    | BibTeX entry              |
| `cod` + <kbd>tab</kbd>    | python code file          |
| `fig` + <kbd>tab</kbd>    | figure block              |
| `fgg` + <kbd>tab</kbd>    | figures block in grid     |
| `fgr` + <kbd>tab</kbd>    | figure (rotated) block    |
| `file` + <kbd>tab</kbd>   | file                      |
| `hd` + <kbd>tab</kbd>     | set heading no.s          |
| `letter` + <kbd>tab</kbd> | letter block              |
| `lnk` + <kbd>tab</kbd>    | url and link label        |
| `ltmpl` + <kbd>tab</kbd>  | letter template           |
| `lscape` + <kbd>tab</kbd> | set page to landscape     |
| `note` + <kbd>tab</kbd>   | note block                |
| `ntmpl` + <kbd>tab</kbd>  | note template             |
| `pb` + <kbd>tab</kbd>     | page break                |
| `ref` + <kbd>tab</kbd>    | reference block           |
| `tbl` + <kbd>tab</kbd>    | table block               |

Some custom snippets (scope specific):

| Snippet                   | Inserts                   |
| ------------------------- | --------------------------|
| `loc` + <kbd>tab</kbd>    | Insert location figure    |
| `mrk` + <kbd>tab</kbd>    | Insert markup dwg rotated |
| `p1` + <kbd>tab</kbd>     | Insert custom fig in grid |
| `strep` + <kbd>tab</kbd>  | Insert fig cf repair(s)   |

These snippets work when the file under edit is set as a Typst file from the pull-up menu in the status bar. (Suggest installing [Typst package][tp].)

## What are snippets and how do they work?

The concept of a snippet is simple. Think of a block of pre-formatted text (i.e., a template) that one needs to use often. One can of-course type or copy-paste such blocks of text repeatedly the hard way, or one could instead assign such common blocks of text with an abbreviated keyword, which in turn calls the entire block of text. To ensure such blocks do not accidentally appear while typing the actual content of the note, paper, or report, a trigger is required. The trigger in this case is a <kbd>tab</kbd> key.

## How to add these snippets to Sublime Text

This is done in two steps, viz., (a) add a repository and then (b) activate it. The how to is described below.

1. From _Tools > Command Palette..._ type _Add Repository_, and in the input box, enter `https://github.com/ckunte/typst-snippets-st`
2. From _Tools > Command Palette..._ type _Install Package_, and in the result list, type `typst-snippets-st` and select the thus found package.

## How to upgrade 

From _Tools > Command Palette..._ type _Upgrade Package_, and select one of the two options presented (i.e., _Package Control: Upgrade Package_ or _Package Control: Upgrade/Overwrite All Packages_).

## Custom build

A custom build file (e.g. like below: `Typst-Cyg.sublime-build`) can be added under _Settings > Browse packages > User_, with file path edited to suit:

```
{
    "shell_cmd" : "typst compile \"$file_name\"",
    "selector" : "source.typ",
    "path" : "C:\\Users\\ckun\\misc\\cyg\\bin;$path",
    "working_dir" : "$file_path"
}
```
Then From _Tools > Build system_, select _Typst-Cyg_. This will enable building (with Ctrl+B) from source to output (i.e. from .typ to .pdf file) from within Sublime Text.

[Typst]: https://typst.app
[st]: https://www.sublimetext.com "Text editing done right."
[tp]: https://packagecontrol.io/packages/Typst
