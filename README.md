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
- `prompt`: whether to prompt for specification in case of multiple matches (see usage)

## Usage

`rbook word` will search for `word` (case-insensitive) in the list of matching filenames in your library. If there is one match, it immediately launches your reader on that file. 

If there are multiple matches, what happens depends on whether the `prompt` option is set or not. This can be forced on or off with the options `-p`/`--prompt` and `-y`/`--no-prompt`, otherwise the `prompt` option in `rbookrc` is checked, else it is enabled by default.

In prompt mode, the program will prompt you to manually choose matches. Any invalid choice (such as an empty string) will exit the program.

In promptless mode, the first match alphabetically is opened with no interactivity required. Promptless mode is particularly convenient if one wants to run `rbook` from a launcher instead of a terminal. In that case it's a good idea to set `prompt = False` in `rbookrc` and use `-p` with the occasional command line use.

`rbook` only uses filenames for matches - no metadata of any kind - but it makes no assumption on the formatting of the filename itself. Any set of .pdf-like files with decently informative filenames will work just fine.
