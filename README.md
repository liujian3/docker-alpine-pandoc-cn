# alpine-pandoc-cn

Pandoc for Chinese based on Alpine Linux.

## Usage

```sh
$ docker pull liujian3lj7/alpine-pandoc-cn
$ docker run -it --rm -v `pwd`:/workspace liujian3lj7/alpine-pandoc-cn pandoc input.md -f markdown -o output.pdf -V documentclass=ltjarticle -V classoption=a4j -V geometry:margin=1in --pdf-engine=lualatex
```

### Use Template

```
$ mkdir templates
$ wget https://raw.githubusercontent.com/Wandmalfarbe/pandoc-latex-template/master/eisvogel.tex -O templates/eisvogel.tex
$ docker run -it --rm -v `pwd`:/workspace -v `pwd`/templates:/root/.pandoc/templates k1low/pandoc:latest pandoc input.md -f markdown -o output.pdf -V documentclass=ltjarticle -V classoption=a4j -V geometry:margin=1in -V CJKmainfont=IPAexGothic --pdf-engine=lualatex --template eisvogel.tex --listings
```

## Reference Dockerfile

- [k1LoW/docker-alpine-pandoc-ja](https://github.com/k1LoW/docker-alpine-pandoc-ja)
