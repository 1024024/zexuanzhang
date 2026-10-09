# Luke's portfolio site

Everything the site shows lives in two places:

- `content/site.json` — your CV and the list of posts (articles, programs, CAD projects)
- `models/` and `images/` — STL/OBJ models, renders, and drawing PDFs

## Add or edit content (on github.com)

1. Upload any new files first: drag them into the `models/` or `images/` folder (use *Add file → Upload files*).
2. Open `content/site.json`, click the pencil icon, edit, and *Commit changes*.
3. The live site updates within a minute or two.

### Post formats

Article:
```json
{ "id": "my-post", "kind": "article", "title": "…", "date": "2026-10-20",
  "summary": "One line", "tags": ["mechanics"], "body": "Markdown text. Use \\n for new lines." }
```

Program (Python, runs in the visitor's browser):
```json
{ "id": "my-program", "kind": "program", "title": "…", "date": "2026-10-20",
  "summary": "…", "notes": "Optional Markdown", "stdin": "default input", "code": "print('hello')" }
```

CAD project:
```json
{ "id": "my-part", "kind": "cad", "title": "…", "date": "2026-10-20", "software": "SolidWorks",
  "summary": "…", "body": "Markdown notes",
  "model": { "path": "models/my-part.stl", "format": "stl", "name": "my-part.stl" },
  "images": ["images/render1.png"], "drawing": { "path": "images/drawing.pdf", "name": "Drawing (PDF)" } }
```

Delete the three posts whose `id` starts with `example-` once you've added your own.

Keep each file under 25 MB (GitHub's web upload limit). Export STL as binary at a coarse/medium resolution.

## Preview on your computer

Opening `index.html` by double-clicking won't load the content (browsers block it). Instead run, in this folder:
`python -m http.server` and visit http://localhost:8000
