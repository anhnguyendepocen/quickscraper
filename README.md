# quickscraper

An R wrapper for the [quickscrape](https://github.com/ContentMine/quickscrape)
web scraping tool.

## Installation

You need `node.js` 0.8 or later installed to run quickscraper.  You can get it
[here](http://nodejs.org/).

In R, run:

```
if(!require(devtools)) install.packge("devtools")
library(devtools)
install_github("noamross/quickscraper")
```

When first loaded, `quickscraper` will ask to install its node module dependencies.
These are not bundled with the package because they contain system-specific
binaries which would not be allowed on CRAN, but by using the node package
manager after the R package install,  the correct ones can be selected and
installed.

The node-wrapping and dependency-checking components of this package (In 
[`R/node.r`](https://github.com/noamross/quickscraper/blob/master/R/node.R)) 
will eventually be extracted into a separate package of utilties for wrapping
arbitrary node modules.

## Usage

Usage is currently very basic, as the `quickscrape` API is still evolving.

The function `scrape()` scrapes information from a url or a set or URLs,
saving the results to disk or returning them to R in the form of a list.
For instance:

```
scrape('https://peerj.com/articles/409/')
```

See `?scrape` for more details and options.

## Notes

Note that this repository contains both
[quickscrape](https://github.com/ContentMine/quickscrape) and
[journal-scrapers](https://github.com/ContentMine/journal-scrapers). These
are handled using `git subtree`.