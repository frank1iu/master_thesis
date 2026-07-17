### Compiling documents using pLaTeX

(To compile `bachelor/main.tex`, change `master` to `bachelor` in line 5 of `docker-compose.yml`)

First, copy `.latexmkrc` to your `master` (or `bachelor`) directory:
```
cp .latexmkrc ../master/.latexmkrc
```

To compile `main.tex`, run:
```
docker compose run --rm platex main.tex
```
The first run can take a while (>5 minutes) due to building the image.

### Helpful cleanup commands

To cleanup temporary files, run:
```
docker compose run --rm platex -c
```

To cleanup temporary files and outputs, run:
```
docker compose run --rm platex -C
```

### Using the LaTeX Workshop extension for Visual Studio Code

1. Install the LaTeX Workshop extension
2. Change settings as follows:
```diff
-   "latex-workshop.docker.enabled": false
+   "latex-workshop.docker.enabled": true
-   "latex-workshop.docker.image.latex": ""
+   "latex-workshop.docker.image.latex": "<name of your image>"
-   "latex-workshop.latex.recipe.default": "first"
+   "latex-workshop.latex.recipe.default": "latexmk (latexmkrc)"
```
Then go to `"latex-workshop.latex.tools"`, find `"latexmk_rconly"` and add these options:
```diff
    {
        "name": "latexmk_rconly",
        "command": "latexmk",
        "args": [
+           "-pdfdvi",
+           "-interaction=nonstopmode",
+           "-halt-on-error",
+           "-file-line-error",
            "%DOC%"
        ],
        "env": {}
    },
```
3. Go to the LaTeX sidebar on the right and find the "View LaTeX PDF" menu. Click "View in VSCode tab".

Note: `synctex` seems to be somewhat working - you can Ctrl+Click (or Cmd+Click on MacOS) the text to go to the corresponding location in the source files.

### LaTeX workshop workaround for subfiles

Add this line to the start of all subfiles (chapter1.tex, chapter2.tex, etc.) to tell LaTeX workshop where to find the root file:

```
% !TEX root = ../main.tex
```