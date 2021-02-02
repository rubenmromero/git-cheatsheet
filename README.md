# Git Cheatsheet

<a href="https://blog.osteele.com/2008/05/my-git-workflow/" target="_blank"><img src="https://rubenmromero.s3.eu-west-1.amazonaws.com/images/git-transport.png" alt="Git Data Transport Commands" class="image"></a>

Command | Purpose
---- | ----
`git status` | Show the status of local and staged changes
`git branch -av` | Show the status of all local and remote branches (those which are fetched to the local repository)
`git init` | Create an empty Git repository or reinitialize an existing one in the folder in which is executed
`git add <file>` | Add the file `<file>` if it is new, or stage the changes made to this if it already exists, in the index
`git add .` | Add all files and pending changes to be staged in the index
`git rm <file>` | Remove the file `<file>` from the working tree and from the index (ready to be commited)
`git checkout <file>` | Discard the changes made in the file `<file>` that are pending to be staged in the index
`git checkout .` | Discard all changes made that are pending to be staged in the index except for new files not yet staged, which are kept in the same state (created in the working tree)
`git commit -m "<message>"` | Commit the changes staged in the index to the local repository using the entered `<message>` as the commit message
`git branch <branch>` | Create the local branch `<branch>`
`git branch -d <branch>` | Delete the local branch `<branch>`
`git branch -D <branch>` | Delete the local branch `<branch>` although it is not completely merged (force)
`git checkout <branch>` | Switch to the existing branch `<branch>` in the repository (local or remote)
`git checkout -b <branch>` | Create the branch `<branch>` from the current branch (it replicates) and switch to it
`git fetch -p` | Update the local repository with the current status of all existing remote branches and tags, removing those that no longer exist on the remote
`git pull` | Update in the current branch the existing changes in the remote linked (upstream) branch
`git push` | Push the commited changes in the current branch to the remote linked (upstream) branch
`git push -u origin <branch>` | Push the commited changes in the current branch to the remote branch `<branch>` creating it in case it does not exist, and linking (setting upstream) the local branch to the remote one
`git push --force` | Push the commited changes in the current branch overwriting the remote linked (upstream) branch
`git push --force-with-lease` | Push the commited changes in the current branch overwriting the remote linked (upstream) branch ensuring that someone else's work (commits added to the remote branch) is not overwritten by force pushing
`git push origin :<branch>` | Delete the remote branch `<branch>`
`git tag <tag> -m "<message>"` | Create the tag `<tag>` in the local repository from the current HEAD (current branch + last commit) using the entered `<message>` as the tag message
`git tag -d <tag>` | Delete the tag `<tag>` in the local repository
`git push --tags` | Push the existing tags in the local repository to the remote
`git push origin :<tag>` | Delete the tag `<tag>` in the remote repository
`git merge <branch>` | Merge the new commits from the branch `<branch>` to the current branch
`git rebase <branch>` | Reapply the new existing commits in the current branch on top of new existing commits in the branch `<branch>` (base)
`git reset HEAD <file>` | Unstage the tracked changes in the index for the file `<file>`, keeping them in the working tree (soft reset)
`git reset HEAD` | Unstage all tracked changes in the index keeping them in the working tree (soft reset)
`git reset HEAD~<n>` | Revert the last `<n>` commits in the current branch keeping all changes made by them in the working tree (soft reset), ready to be staged again by executing the corresponding `git add` commands, or definitively discarded by executing the `git checkout .` command
`git reset --hard origin/<branch>` | Discard all commits and changes made in the current branch (staged or not) overwriting it to the current state of the remote branch `<branch>` (hard reset), whether or not this is linked to the current branch
`git stash`* | Stash all pending changes to be commited (staged or not) in a dirty working directory away except for new files not yet staged, which are kept in the same state (created in the working tree)
`git stash pop`* | Recover previously stashed changes through the `git stash` command in the current branch

\* These commands are very useful when there are pending changes to be commited in the current branch, and it is needed to switch (`git checkout`) to a different branch, in order to prevent it from trying to carry them to the switched branch.
