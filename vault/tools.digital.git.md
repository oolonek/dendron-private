---
id: 99ce9016-5209-48d5-850c-046a18555453
title: Git
desc: ''
updated: 1611659348475
created: 1609525494924
stub: true
---

# Get info of the git remote

`git config --get remote.origin.url`

# Get history as a graph

```
git fetch
git log --all --decorate --oneline --graph
```


# Pull

https://stackoverflow.com/a/4924044

So I imagine you want to do something like:

`git pull origin dev`

To set it up so that it does this by default while you're on the dev branch:

`git branch --set-upstream-to dev origin/dev`

