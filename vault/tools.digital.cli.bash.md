---
id: 0d1b1c57-d5bc-4770-8ebf-2aee07495b98
title: Bash
desc: ''
updated: 1611135215965
created: 1610975606358
---

# Rename files

```bash
for f in *.png; do echo mv "$f" "${f/_*_/_}"; done
```

Remove echo 

https://stackoverflow.com/a/24103055

[[#tremendous|tag.tremendous]]

# List all files and folder in a graphical tree in terminal

You need to 
`brew install tree`

Then you can `tree` or `tree -lart`

