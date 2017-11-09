# nuweb
Nuweb fork from nuweb.sourceforge.net

I forked Nuweb vs. 1.58 from the Sourceforge repository because I need a
possibility to install Nuweb automatically from an open
repository. Installation from Sourceforge needs a manual intervention.

## Original documentation

Here's an intermediate version of nuweb.  We've bundled up the
web source (`nuweb.w`), the generated `.c` files, file, and the assorted
auxiliary files for latex'ing with a Makefile.

Note that it's still not completely portable to every system without
change.  In particular, it expects file-names to use '/' to delimit
directories which is OK unless you are on MSDOS (where it's '\') or
VMS (which uses ':' and ']') and it thinks tab stops are set every
eight spaces.

To print the documentation, you must first run LaTeX on the file
`nuwebdoc.tex`.  To fix up all the citations, you'll need several runs.

`	latex nuwebdoc
	bibtex nuwebdoc
	latex nuwebdoc
	latex nuwebdoc
`
Note that the distributed nuwebdoc.tex is basically Chapter 1 of the
complete nuweb.tex generated by running nuweb against itself.

To actually build the nuweb executable, type `make nuweb` which should
build an executable file called `nuweb`.  After that, you should be
able to use the makefile to control everything very nicely.

To view the nuweb sources using an HTML viewer, copy `nuweb.w` to
nuweb.hw, and then add the html document-style option to nuweb.hw.
After producing the LaTeX source file nuweb.tex, convert it to HTML
using LaTeX2HTML.

For the latest version check the [SourceForge page:](http://nuweb.sourceforge.net/)


### Changes in Version 1.58:
* Supress indentation for one fragment or argument
* Allow fragment expansion in tex.

### Changes in Version 1.57:
* Fixed SF3416213, \it deprecated in LaTeX2e, use \itshape
* Fixed SF3431294, Fragment page number refs don't work in memoir class
* Fixed SF3432035, -d output file flag doesn't work
* Removed use of hyperref parameter dvipdfm (-> error in TeX Live 2011)

### Changes in Version 1.56:
* Added minor command @t to include fragment title in output files.
* Fragment use embedded in fragment argument is no longer commented.
* Make tar now produces top level versioned directory.

### Changes in Version 1.55:
* Fixed bug 3168635 (doesn't handle inability to create output files).

### Changes in Version 1.54:
* Fixed bug 3158592 (SEGV) by reworking sentinel-based scrap processing.
* Fixed bug 3160408 by defining MAX_NAME_LEN (to 1024) in global.h.