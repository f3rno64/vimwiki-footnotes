## Footnotes for vimwiki

~~This fork is a slight tweak of the venerable [vimfootnotes][], for use with
extended markdown( Whereas the original script inserts footnotes that look like
this~~

This fork of a fork is a slight tweak to adapt to vimwiki's syntax.
**beware**: I may prepare a pull request for [Konfekt's fork](https://github.com/Konfekt/vim-markdownfootnotes) at some point.

For vimwiki, it a footnote mark would look like this:

~~~
Here is some text.<sup>[[#1]]</sup>

* *1*: Here is a note.
~~~

To insert a footnote, hit `<Leader>f` in normal mode or type `[]`. Then

- A footnote mark will be inserted after the cursor,
- A matching footnote mark will be inserted at the end of the file, and
- a split window at the bottom will open, ready to edit the new footnote.

When done, type `ZZ` to close the split and return to the main text.

## Installation

Drop `vimwiki-footnotes.vim` in your plugin directory.

(Tip: use [minpac](https://github.com/k-takata/minpac))

## Settings

By default, footnote ids are arabic numerals. You can change this by
setting `b:vimfootnotetype`:

+	`arabic`: 1, 2, 3...
+	`alpha`:  a, b, c, aa, bb..., zz, a...
+   `Alpha`:  A, B, C, AA, BB..., ZZ, A...
+   `roman`:  i, ii, iii... (displayed properly up to 89)
+   `Roman`:  I, II, III...
+   `star`:   \*, \*\*, \*\*\*...

## Commands

`AddVimFootnote`
 :  inserts footnotemark at cursor location, inserts footnotemark on new
    line at end of file, opens a split window all ready for you to enter in
    the footnote.

`ReturnFromFootnote`
 :  closes the split window and returns to the text in proper place.

These are mapped to `<Leader>f` and `<Leader>r` respectively.

`FootnoteNumber`
 :  Change the current footnote number (one obligatory argument)
    :FootnoteNumber 5

`FootnoteNumberRestore`
 :  Restore old footnote number  

`FootnoteUndo`
 :  Decrease footnote counter by 1

`FootnoteMeta [<footnotetype>]`
 :  Change type of the footnotes and restart counter (1, a, A, i, I, *)

The `<footnotetype>` argument is optional. If omitted, and your previous
footnote type was not `arabic`, the new type will be `arabic`; if it was
arabic, the new type will be `alpha`. If the new type is the same as the
previous type, then the counter will not be restarted.


`FootnoteRestore`
  : Restore previous footnote type and counter.

## Todo

1.  It would not be hard to add support for other plaintext footnote
    formats, triggered by filetype.

 [vimfootnotes]: http://www.vim.org/scripts/script.php?script_id=431
