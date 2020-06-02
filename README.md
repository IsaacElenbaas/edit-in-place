# edit-in-place
Takes stdin and rewrites only what has to be rewritten of an existing file. I read [this](https://backreference.org/2011/01/29/in-place-editing-of-files/) but thought I could get it working well. Not only does it edit in-place, it leaves bytes that don't need to change alone.

### This uses `dd`, `>>`, and `truncate` to rewrite only the bytes of a text file that need to be rewritten.
Please don't use it anywhere important, but it seems to be working. I'm going to have my todo list program use it to see if I can't catch anything that breaks.

Simply call with a path and pipe the entire final content.
`-v` will show the octal of the new and current content, whether the script thinks they match, and the write output.
There are no checks for write permissions (you really shouldn't be using this anywhere important enough to have write protection) as it allows you to change permissions and use `-v` to see exactly what will happen.

<sup><sub>Next we make something to only overwrite the *bits* that need to be changed!
