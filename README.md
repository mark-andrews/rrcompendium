
<!-- README.md is generated from README.Rmd. Please edit that file -->

# A reproducible research compendium example

This repository provides an example of a *reproducible research
compendium*. The analysis that it does is essentially a toy example, but
how it works is general enough (albeit with perhaps some small
modifications and additions) to be useful for most small to medium sized
data analysis projects.

One of the first papers to articulate the general concept of a
reproducible research compendium, especially one that uses R based
tools, was [Statistical Analyses and Reproducible
Research](https://biostats.bepress.com/bioconductor/paper2/) by
Gentleman and Temple Lang in 2004 (also published in 2007 in [Journal of
Computational and Graphical
Statistics](https://www.jstor.org/stable/27594227). Gentleman and Temple
Lang defined a research compendium as an archive that includes all the
original raw data and computer code necessary to reproduce all the
analyses reported in a research study, but in addition includes one or
more *dynamic documents* that produce all of the reports (e.g., the
manuscript for publication, the supplementary documents, slides for
presentations, etc) with all the figures, tables, and other numerical or
statistical quantities that constitute the communicated results of the
analysis. From a compendium, anyone ought to be able to exactly
reproduce every step of the analysis, including intermediate results and
data sets, on the basis of the original raw data, and also should be
able to determine exactly how any figure, table, numerical and
statistical etc any reports was obtained.

When Gentleman and Temple Lang wrote [Statistical Analyses and
Reproducible
Research](https://biostats.bepress.com/bioconductor/paper2/) many tools
that facilitate the creation of a research compendium were either not
well known or simply did not exist at all. These tools include *Git*,
*GitHub*, *RMarkdown*, *knitr*, *pandoc*, *devtools*, *docker*,
*travis*, etc. As a result, at that time, producing a research
compendium was a time consuming and arduous task. By contrast, now that
the tools just mentioned are well known and widely used, producing a
research compendium is remarkably easier. Of course, it still requires
effort and commitment, but this is well worth it because of the
transparency and quality control guarantees that it brings to your work
and because it will allow others, including and especially your future
self, to understand and reproduce your analysis exactly.

# How to use this compendium

There are a number of different ways to use this compendium. In any
case, the first step is always the same: clone the repository from
GitHub.

    git clone https://github.com/mark-andrews/rrcompendium.git

Then open the *RStudio project* that is within the compendium by going
to *File / Open Project* in RStudio and choosing the
`rrcompendium.Rproj` file.

## Use the `analysis.Rmd` RMarkdown file in an normal RStudio session

The simplest way of using this compendium is to just open the
`analysis.Rmd` file in a normal RStudio session, and either render to a
pdf or use it interactively as a
[notebook](https://bookdown.org/yihui/rmarkdown/notebook.html).
Proceeding this way could work just fine. However, even under normal
circumstances it will requires some manual installation of R packages,
as we’ll see. But more, when things start getting complex — when there
are lots dependencies, or when very specific versions of dependencies
are required, or when additional external software or libraries are
required — this simple way might not work, or at least without a lot of
time and effort and patience on the part of the user.

To proceed in this normal ways. You can open the *RStudio project* in
the compendium by going to *File / Open Project* in RStudio and choosing
the `rrcompendium.Rproj` file.

You can then open the `analysis.Rmd` RMarkdown file that is in the
`analysis` directory.

To be able to use `analysis.Rmd` fully, you first need to ensure your
your R/RStudio is set up rendering RMarkdown documents to pdf. You
require the R package `rmarkdown`, but also you need the external
software [pandoc](https://pandoc.org/) and
[TeX/LaTeX](https://www.latex-project.org/). RStudio (since version
v0.98.932) comes bundled with `rmarkdown` and `pandoc`, so you may have
these already. However, it is generally a good idea to use the latest
version of RStudio always and always keep your R packages up to date.
You can do the latter from the RStudio console as follows:

``` r
update.packages(ask = FALSE)
```

Or, to just update `rmarkdown`, do

``` r
install.packages('rmarkdown')
```

Installing [TeX/LaTeX](https://www.latex-project.org/) can be done in
different ways depending on the platform (Windows, Mac OSX, Linux) that
you use. If, however, you just want to use TeX/LaTeX within RStudio for
rendering RMarkdown files to pdf, then (by far) the easiest option is to
install [tinytex](https://yihui.name/tinytex/) as follows:

``` r
install.packages('tinytex')
tinytex::install_tinytex()
```

You also need to install the special purpose `rrcompendium` R package
that accompanies this compendium. This is installed as follows:

``` r
devtools::install_github('mark-andrews/rrcompendium')
```

Installing this package will also install all the R dependencies you
need.

Now you can render `analysis.Rmd` to a pdf by pressing the *Knit* button
on the source file editor tab, or select `File / Knit Document`, or
(best option, in my opinion) press `Ctrl + Shift + K`.

You can also
