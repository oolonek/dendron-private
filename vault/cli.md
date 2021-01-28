---
id: 9d275a55-3465-45f7-91b4-ff2ba5435ee2
title: CLI
desc: ''
updated: 1611599278358
created: 1611130406336
stub: false
---


# find files and order by date 

find ~/ -type f -name "*.key" 2> /dev/null | xargs -0 ls -tl


