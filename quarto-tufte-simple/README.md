# Tufte-LaTeX Quarto Extension

This extension converts Quarto Markdown files to LaTeX using the Tufte-LaTeX document classes.

## Usage

### Generate LaTeX from QMD

To convert a Quarto Markdown file to LaTeX using the Tufte template:

```bash
uv run quarto pandoc sample-book.qmd --template=_extensions/tufte/template.tex -o output.tex
```

### Compile to PDF

Once you have the LaTeX file, compile it with your preferred LaTeX engine:

```bash
pdflatex output.tex
pdflatex output.tex  # Run twice for references
```

## Files

- `sample-book.qmd` - Example Quarto document with Tufte content
- `sample-book-original.qmd` - Complete reproduction of original sample-book.tex content
- `_extensions/tufte/template.tex` - LaTeX template that mirrors original sample-book.tex
- `tufte-book.cls`, `tufte-handout.cls`, `tufte-common.def` - Tufte document classes
- `sample-handout.bib` - Bibliography file
- `graphics/` - Contains all figures and images referenced in the document

## Output

The generated LaTeX file will use the `tufte-book` document class and produce output identical to the original sample-book.tex when compiled.