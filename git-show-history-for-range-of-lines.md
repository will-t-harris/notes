---
id: git-show-history-for-range-of-lines
aliases: []
tags: []
---

# Git Show History for Range of Lines

`git log -L<line number>,<offset>:<path to file>`

This opens a buffer that shows the sequence of commits in the git history that have affected the line/range, allowing you to more easily trace the evolution of the range specified.

Can also provide a regex instead of a line number, to get the history of the first line that matches the regex.
