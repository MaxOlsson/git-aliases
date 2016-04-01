```
[alias]
	lg = log --graph --oneline --decorate=full --branches
	ld = log --pretty=format:"%C(yellow)%h\\ %ad%C(red)%d\\ %Creset%s%C(green)\\ [%cn]" --decorate --date=default
	newl = checkout -b
	sup = "!git push --set-upstream origin \"$(git rev-parse --abbrev-ref HEAD)\" "
	get = !sh -c \"git checkout $1 && git up\"
	fdel = "!f(){ git branch -D ${1} ; git push origin --delete ${1}; };f"
	binf = !git for-each-ref --format='%(committerdate:local) %09 %(authorname) %09 %(refname:short)'
	rename = "!f(){ git branch -m ${1} ${2} ; git push origin --delete ${1} ; git push --set-upstream origin ${2} ; };f"
	up = "!git remote update -p; git merge --ff-only @{u}"
	fpush = "!git push origin \"$(git rev-parse --abbrev-ref HEAD)\" --force"
	st = status
	co = checkout -- .