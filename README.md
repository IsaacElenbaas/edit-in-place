# edit-in-place
Takes stdin and rewrites only what has to be rewritten of an existing file. I read [this](https://backreference.org/2011/01/29/in-place-editing-of-files/) but thought I could get it working well. Not only does it edit in-place, it leaves bytes that don't need to change alone.

### This uses `dd`, `>>`, and `truncate` to rewrite only the bytes of a text file that need to be rewritten.
Please don't use it anywhere important (or at all, really), but as far as I can tell it is stable.

Simply call with a path and pipe the entire final content.
`-v` will show the octal of the new and current content, whether the script thinks they match, and the write output.
There are no checks for write permission as it allows you to deny it and use `-v` for a dry run.

<sup><sub>Next we make something to only overwrite the *bits* that need to be changed!
