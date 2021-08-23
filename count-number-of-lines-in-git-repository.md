```bash
git ls-files | xargs wc -l 
```
- `git ls-files` outputs all the tracked file names
- `xargs wc -l` for each file name(`xargs`), count the number of newlines(`wc -l`)

## You can throw a grep in to get line counts for specific parts of the repo

```bash
git ls-files | grep -P ".*(jsx|tsx)" | xargs wc -l
```
- greps for the perl regex provided
---

[Related SO](https://stackoverflow.com/questions/4822471/count-number-of-lines-in-a-git-repository)