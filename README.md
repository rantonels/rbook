`rbook` is a simple, no-bs reader command-line launcher for a folder of document files. It's particularly suited to libraries of books for fast consultation.

## Installation

After a clone, run

```
sudo pip install .
```

Also, copy `rbookrc` to `~/.config/rbookrc` and edit to your pleasure. Fields:

- `path`: path where documents are stored
- `reader`: command for document reader (`evince`, `zathura`...)
- `extensions`: file extensions to search for, commma-separated

## Usage

`rbook word` will search for `word` (case-insensitive) in the list of matching filenames in your library. If there is one match, it immediately launches your reader on that file. If there are multiple matches, it will prompt you to manually choose matches. Any invalid choice (such as an empty string) will exit the program.

`rbook` only uses filenames for matches - no metadata of any kind - but it makes no assumption on the formatting of the filename itself. Any set of .pdf-like files with decently informative filenames will work just fine.
