## Background
- I'm not an expert on git
- I've used SVN, BZR and GIT (and CVS once).
- Used SVN for all my personal files since 2005
- Been using GIT since 2011 for everything
- I prefer rebase to merge due to cleaner history and more control over the outcome of conflicts.
- I prefer rebase since it puts the onus on the developer to make sure the main branch is in a good state.

```
code .
git init
git add README.md
git add index.js
git add .tool-versions
git commit -m "first commit"
git remote add origin git@github.com:StefanWallin/grebase.git
git push -u origin main
open https://github.com/StefanWallin/grebase
```

```
git checkout -b emoji
```

**Edit 1: (emoji)**
```
console.log("Violets are 🔴,")
console.log("Roses are 🔵,")
```

```
git add -p
git commit -m "Use emojis for colors"
git push -u origin emoji
```
- Make PR
- Do not merge PR

```
git checkout main
```

**Edit 2: (main)**
```
console.log("Roses are red,")
console.log("Violets are blue,")
```

```
git add -p
git commit -m "Correct the poem"
git push
```

- open PR again - see conflict
- LET'S REBASE! 🎉
```
git pull
git checkout emoji
git rebase -i main
  talk about the file
  talk about EDITOR
  pick
  :wq
```
- `git status`
- `git status -sb`
- Source tree
- **Edit 3: (emoji)**
- Resolve conflict
- Save file
- `git add index.js`
- `git rebase --continue`
- REBASE DONE 🍾
- `git push`
- Try sync button in VS Code
- Try push button in Source Tree
- 🤦‍♂️ 😱
- `git push --force-with-lease` vs `git push --force`
- `git checkout -b emoji2`
- `git push -u origin emoji2`
- `git checkout emoji`
- `git push --force-with-lease`
- Kolla PR igen



**Edit 4: (hooja)**
git checkout HEAD^
git commit -m
```
console.log("Lingon är röda,")
console.log("Älgen är blå,")
console.log("Du gillar brännvin,")
console.log("Fyfan då är vi två")
```