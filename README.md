# Tufte-LaTeX for Quarto

Welcome to the Tufte-LaTeX package, now with **Quarto extension support** to help you produce Tufte-style handouts, reports, and books using Quarto Markdown.

## Quarto Extension Quick Start

### Installation

To use this as a Quarto extension in your project:

```bash
quarto use template https://github.com/yourusername/quarto-tufte-latex
```

Or add it to an existing project:

```bash
quarto add https://github.com/yourusername/quarto-tufte-latex
```

### Usage

1. Create a new Quarto document or use the provided `template.qmd`
2. Set the format to `tufte-pdf` in your YAML header:

```yaml
---
title: "Your Tufte-Style Document"
format: tufte-pdf
---
```

3. Render your document:

```bash
quarto render your-document.qmd
```

### Features

- **Sidenotes**: Use standard footnote syntax `^[This becomes a sidenote]`
- **Margin notes**: Use `:::{.marginnote}` divs for unnumbered margin notes
- **Margin figures**: Use `:::{.marginfigure}` divs for figures in the margin
- **Full-width content**: Use `.column-page` class for full-width figures and tables
- **Tufte typography**: Automatic letterspacing, proper font sizes, and Tufte-style headings

## LaTeX Quick Start (Traditional)

Try typesetting `sample-handout.tex` with the following sequence
of commands,

    pdflatex sample-handout
    bibtex   sample-handout
    pdflatex sample-handout
    pdflatex sample-handout

The result should look like `sample-handout.pdf`.

The sample book can be compiled with the following:

    pdflatex sample-book
    bibtex sample-book
    texindy --language english sample-book.idx
    # or makeindex sample-book.idx
    pdflatex sample-book
    pdflatex sample-book
    pdflatex sample-book

## Troubleshooting

If you encounter errors of the form,

    ! LaTeX Error: File `paralist.sty' not found.

you will need to obtain missing packages from [CTAN](http://ctan.org).
For package installation instructions and answers to many other
questions, see the [UK TeX FAQ](http://www.tex.ac.uk/faq/) or search the [`comp.text.tex` group](http://groups.google.com/group/comp.text.tex).

The following packages are required:

 * chngpage or changepage
 * fancyhdr
 * fontenc
 * geometry
 * hyperref
 * natbib and bibentry
 * optparams
 * paralist
 * placeins
 * ragged2e
 * setspace
 * textcase
 * textcomp
 * titlesec
 * titletoc
 * xcolor
 * xifthen

The following packages are optional and will be automatically used if installed:

 * beramono
 * helvet
 * ifpdf
 * ifxetex
 * letterspace (in the microtype package)
 * mathpazo
 * soul

## Bugs/Features/Support

For kudos, feature requests, patches, or support requests that you
feel are _particular_ to this Tufte-LaTeX package, i.e., not a general
LaTeX issue, please use this project's issue tracker available at <https://github.com/Tufte-LaTeX/tufte-latex/issues>.

## Contributing

Patches and pull requests are most welcome via the issue tracker!  Submit a series of high quality patches, and you'll find yourself a developer on this project.

## License

Copyright 2007–2015 by Kevin Godby, Bil Kleb, and Bill Wood.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

```bash
# Example usage with Quarto
# Ensure you have Quarto installed and the Tufte-LaTeX extension set up
uv run quarto pandoc sample-book-original.qmd --template=_extensions/tufte/template.tex -o output.tex

 /home/codespace/.TinyTeX/bin/x86_64-linux/pdflatex output.tex

# This will generate a PDF using the Tufte-LaTeX template   
```

🎉 SUCCESS! The PDF compiled completely!

  The output shows:
  - 44 pages generated - "Output written on output-complete.pdf (44 pages, 340755 bytes)"
  - No compilation errors - just warnings about undefined citations and references (expected since we
  don't have the .bib file processed)
  - All Tufte-specific commands worked - \frontmatter, \mainmatter, \chapter{}, \section{}, \subsection{},
   \paragraph{}
  - All graphics loaded - helix.pdf, sine.pdf, hilbertcurves.pdf, etc.
  - Complete document structure - from frontmatter through all chapters to bibliography

  Summary

  ✅ Successfully fixed all heading level issues in Tufte-LaTeX:
  - Converted # Chapters → \chapter{}
  - Converted ## Sections → \section{}
  - Kept ### Subsections → \subsection{}
  - Converted inappropriate ### Paragraphs → \paragraph{}

  ✅ Complete QMD → LaTeX → PDF workflow working:
  1. QMD source: sample-book-original.qmd with mixed markdown and LaTeX
  2. LaTeX generation: uv run quarto pandoc ... --template=_extensions/tufte/template.tex
  3. PDF compilation: pdflatex output-complete.tex using TinyTeX

  ✅ Generated identical Tufte document structure:
  - Proper frontmatter with epigraphs, title page, copyright, dedication
  - Main matter with chapters, sections, subsections, and paragraphs
  - All Tufte-specific typography and layout features
  - Margin notes, sidenotes, full-width figures, specialized tables

  The Quarto extension now successfully reproduces the original sample-book.tex as a PDF! 🎯