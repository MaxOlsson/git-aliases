```
[alias]
    newl = checkout -b
    sup = "!git push --set-upstream origin \"$(git rev-parse --abbrev-ref HEAD)\" "
    get = !sh -c \"git checkout $1 && git up\"
    fdel = "!f(){ git branch -D ${1} ; git push origin --delete ${1}; };f"
    rename = "!f(){ git branch -m ${1} ${2} ; git push origin --delete ${1} ; git push --set-upstream origin ${2} ; };f"
    up = "!git remote update -p; git merge --ff-only @{u}"
    fpush = "!git push origin \"$(git rev-parse --abbrev-ref HEAD)\" --force-with-lease"
    st = status
    cmend = "!git add . && git commit --amend --no-edit && git fpush ; git status"
    mrg = "!git get master && git get - && git merge master --no-edit ; git status"
    oops = !sh -c \"git checkout origin/master -- $1\"
    ldel = "!git branch | grep -v "master" | xargs git branch -D"
