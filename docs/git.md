## Cleaning out already merged branches

```
git branch --merged | grep -v "\*" | xargs -n 1 git branch -d
```


## Update all submodules in folder

```
for d in */; do (cd "$d" && git pull); done
```
