# edumath
A collection of resources for math teachers

## Convert markdown to pdf

### Without images (shell with a container)

1. Add to your shell profile an alias

``` shell
alias md2pdf='function f(){ docker run -it --rm -v "$(PWD):/root/shared/folder" --name md2pdf --entrypoint pandoc pdflatex "$1" -V geometry:a4paper -V geometry:margin=2cm  -o "${1%.*}".pdf ; unset -f f; }; f'
```

2. Run this command to generate a PDF
``` shell
md2pdf < markdown file name >
```

### With images (in VS Code)

1. Install extension "Markdown PDF"

2. With a markdown file selected, press F1

3. Pick "Markdown PDF"

4. (auto) A new pdf file is generated in the same directory