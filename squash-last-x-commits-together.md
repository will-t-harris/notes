```bash
git log -1 --oneline # This allows us to get the present state's commid-id

git reset --soft HEAD~3 # go back 3 commits, sort of "forgets" that these commits were previously made

git commit -m <NEW_MESSAGE> # fold all the previous commits into this single commit
```
0f07bec0
---

[Related SO](https://stackoverflow.com/questions/5189560/squash-my-last-x-commits-together-using-git)