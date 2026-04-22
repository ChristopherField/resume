# Build Instructions
## Prerequisites
- podman -- install via latest instructions
- shell e.g. sh can use wsl on windows
- download github style sheet from https://github.com/sindresorhus/github-markdown-css  
specifically need github-markdown.css
## Build docker container
./pan-weasy.sh
## convert to pdf

Basically conver to html and then combine with github-markdown.css style sheet (handled via github-template.html) before converting to pdf via weasyprint.

```
podman run -v "$(pwd):/data" localhost/pandoc-weasy pandoc /data/ChrisFieldResume_2025_Markdown.md --from gfm -o ChrisFieldResume_2025_Markdown.html --template=github-template.html

podman run -v "$(pwd):/data" localhost/pandoc-weasy weasyprint /data/ChrisFieldResume_2025_Markdown.html /data/ChrisFieldResume_2025_Markdown.pdf
```

## convert to doc

```
podman run -v "$(pwd):/data" localhost/pandoc-weasy ChrisFieldResume_2025_Markdown.md -f gfm -o ChrisFieldResume_2025_Markdown.docx
```

## TODO

Automate resume build

