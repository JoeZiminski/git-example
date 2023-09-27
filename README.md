
Note as a general rule do not force push to shared
branches.

This commit history has some mistakes.

Hey, I made a change over here. First, lets rebase onto main from our branch.

`git rebase main -i`
`git push -f`

Firstly, the most recent commit
should have added "f" and "g" but only 
added "f". We can pin recent changes into the 
last commit. Make the changes then,

`git add .`
`git commit --amend`
`git push -f`

Next, one of the commit messages is mis-spelt.
We can fix it with:

`git rebase HEAD~5 -i`
change the commit to "r", exit and reword.
"git push -f"

We can also do other changes like drop a commit,
or squash one commit into the last.

Finally, there is a mistake on `var_c` which
equals "p" but shoulud be "c". We can fix this
as if we never made the mistake.

Make the change on the file, then

`git commit --fixup <commit id>`
`git rebase HEAD~5 -i --autosqash`
`git log` to check
`git push -f`

