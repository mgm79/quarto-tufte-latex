# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is the Tufte-LaTeX project, providing LaTeX document classes (`tufte-book` and `tufte-handout`) that implement the design principles of Edward Tufte's books and handouts. The classes are known for extensive use of sidenotes, tight integration of graphics with text, and distinctive typography.

## Core Architecture

### Document Classes
- **tufte-book.cls**: Book document class extending LaTeX's book class
- **tufte-handout.cls**: Handout document class extending LaTeX's article class  
- **tufte-common.def**: Shared code and definitions used by both classes

### Key Components
- **Class Options**: Extensive customization via options like `a4paper`, `sfsidenotes`, `twoside`, `symmetric`, `justified`, `debug`
- **Marginal Material**: Sidenotes, margin notes, captions, and citations positioned in wide margins
- **Typography**: Custom font sizing, letterspacing for small caps, and specialized environments
- **Float Handling**: Custom figure/table environments (`marginfigure`, `margintable`, `figure*`, `table*`)

## Development Commands

### Building Sample Documents
```bash
# Compile sample handout
pdflatex sample-handout
bibtex sample-handout
pdflatex sample-handout
pdflatex sample-handout

# Compile sample book
pdflatex sample-book
bibtex sample-book
texindy --language english sample-book.idx  # or makeindex sample-book.idx
pdflatex sample-book
pdflatex sample-book
pdflatex sample-book
```

### Required LaTeX Packages
Essential packages: chngpage/changepage, fancyhdr, fontenc, geometry, hyperref, natbib, bibentry, optparams, paralist, placeins, ragged2e, setspace, textcase, textcomp, titlesec, titletoc, xcolor, xifthen

Optional packages: beramono, helvet, ifpdf, ifxetex, letterspace (microtype), mathpazo, soul

## File Structure

### Sample Files
- `sample-book.tex` / `sample-book.pdf`: Comprehensive book example demonstrating all features
- `sample-handout.tex` / `sample-handout.pdf`: Handout example with bibliography
- `sample-handout.bib`: Bibliography file for handout

### Graphics
- `graphics/`: Contains PDF images, Asymptote source files (.asy), and example graphics
- Graphics are referenced from LaTeX using `\graphicspath{{graphics/}}`

### Customization Hooks
The classes look for local customization files:
- `tufte-common-local.tex`: Common customizations for both classes
- `tufte-book-local.tex`: Book-specific customizations  
- `tufte-handout-local.tex`: Handout-specific customizations

## Key Features

### Sidenotes and Marginal Material
- `\footnote{}` automatically converts to sidenotes
- `\marginnote{}` for unnumbered margin notes
- `\sidenote[number][offset]{text}` for manual control
- Extensive customization options for justification and fonts

### Specialized Environments
- `marginfigure` / `margintable`: Figures/tables in margins
- `figure*` / `table*`: Full-width figures/tables
- `fullwidth`: Text spanning full page width
- Custom caption positioning and alignment controls

### Typography Controls
- `\newthought{}`: Small caps opening for new sections
- `\allcaps{}` / `\smallcaps{}`: Properly letterspaced capitals
- Custom font size hierarchy optimized for readability