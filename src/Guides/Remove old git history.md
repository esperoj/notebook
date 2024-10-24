## Remove old history

```bash
git checkout --orphan latest_branch 
git add -A
git commit -am "init [skip ci]"
git branch -D main
git branch -m main
git push -f origin main
```