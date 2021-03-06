# Summary

The Bluebook package works (only!) with Biblatex (v 2.0 or later) and Biber (v 1.0 or later).
This project is my (ongoing) attempt to modify Paul Stanley's implementation of the OSCOLA citation system to conform to The Bluebook standard. 
Some signifiacnt changes have been made so far, arguably to the point where this has become usable in most cases. Due to the Bluebook's complexity, it is unlikely that this package will ever be a complete solution, but it is my hope that this project will become as useful for those that need to use The Bluebook as [oscola-biblatex](https://github.com/PaulStanley/oscola-biblatex) has been for me (that is to say, very).
For further information about coverage see the documentation (when it has been added).

# Files and licence

## The package

The package consists of five principal files (`bluebook.bbx`, `bluebook.cbx`, and three language definition files,
`english-bluebook.lbx`, `british-bluebook.lbx`, and `american-bluebook.lbx`). <!--There is also a very short index
style file, `bluebook.ist`.--> Those files are derived from those in [oscola-biblatex](https://github.com/PaulStanley/oscola-biblatex) 
and are copyright (c) Paul Stanley 2012-20. Modifications to those files are copyright (c) Joseph Godfrey 2019-20. For a list of modifications made, please refer to the commit history of this repository.

This work may be distributed and/or modified under the conditions of
the LaTeX Project Public License, either version 1.3 of this license
or (at your option) any later version.

The latest version of the license is in [available online](http://www.latex-project.org/lppl.txt) 
and version 1.3 or later is part of all distributions of LaTeX version 2005/12/01 or later.

This work has the LPPL maintenance status 'maintained'. The current
maintainer of this work is Joseph Godfrey.

<!--
## The documentation

The documentation consists of `oscola.tex`, `oscola.pdf` and
`oscola-examples.bib`. Those files are distributed under the Creative
Commons Attribution 3.0-Unported License (CC BY 3.0). A copy of that
license is available [online](http://creativecommons.org/licenses/by/3.0/deed.en_GB).
-->

## Statement of Nonaffiliation
NOT AUTHORIZED BY NOR IN ANY WAY AFFILIATED WITH: The Columbia Law Review Association, Inc., The Harvard Law Review Association, the University of Pennsylvania Law Review, The Yale Law Journal Company, Inc., or The Bluebook® A Uniform System of Citation®.

# Usage

This package is forked from [oscola-biblatex](https://github.com/PaulStanley/oscola-biblatex), for the time being that package's documentation is fine for most use cases, but do note that the formatting differs in this package. 

Added in this package is support for constitutions and support for United States statutes.

## Constitutions

The constitution datatype adds support for the US constitution and state constitutions. To produce a citation for section one of the 14th amendment, simply add the following to your bibliography:
```
@constitution{USConstXIV,
	title={U.S. Const},
	subdivision={amend},
	amendment ={XIV},
	section = {1},
}
```

To produce a citation for Section 7 of Article 10 of the Texas Constitution, add the following to your bibliography:
```
@constitution{TexArt10s7,
	title={Tex. Const},
	subdivision={art},
	amendment ={10},
	section = {7},
}
```
As anything can be entered into the subdivision box, preambles (pmbl.) are supported.

## US Statutes

Support for both federal and state statutes has been added to the legislation datatype. Do note that "US" needs to be entered as a keyword. References to the US code can be done as follows:
```
@legislation{USCPiracy,
  title = {Piracy under law of nations},
  volume = {18},
  journaltitle = {U.S.C.},
  year = {2018},
  pagination = {section},
  keywords = {us}
}
```
Pagination may be ```section``` or ```sections```, specific sections are referenced by pinpoint citations. For the above example, the citation would be ```\cite[1651]{USCPiracy}```.

Similarly, state statutes can be entered like this:
```
@legislation{IdahoWeights,
	journaltitle = {Idaho Code Ann.},
	series = {71}, %title
	pagination = {section},
	year = {1999},
	keywords = {us}
}
```

<!--
## Bug reports

All bug reports, questions, or suggestions should be sent to the
maintainer, whose email is pstanley@essexcourt.net.
-->

# Installation

Simply place

* `bluebook.bbx`: in the package directory `...tex/latex/bluebook`
* `bluebook.cbx`: in the package directory `.../tex/latex/bluebook`
* `english-bluebook.lbx`: in the package directory `.../tex/latex/bluebook`
* `british-bluebook.lbx`: in the package directory `.../tex/latex/bluebook`
* `american-bluebook.lbx`: in the package directory `.../tex/latex/bluebook`
<!--
* `bluebook.pdf` and `bluebook.tex`: with documentation under `.../doc/latex/bluebook`
* `bluebook.ist`: with the index style files in  `.../makeindex/bluebook`
-->

If you use Overleaf, these files can be placed in your project's root directory and they should just work.

<!--
# Version history
Some Point     Version 1      Original release
-->
