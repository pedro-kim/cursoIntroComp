NOTEBOOK: GIT COURSE

    SECTION 3: Git's Essential

        File's Life Cicle:

            1) Untracked: the file can exist, but git won't track it yet (you can track the file by adding the file (git add))

            2) Unmodified: the file has already been added, but it can be modified at any moment and it won't affect its commit.

            3) Modified: you've already added the file, but since you modified it, it must be added again to the stage version to create a commit of it.

            4) Staged: the file is ready to commit, and any modification won't be seen by git unless you add it before the commit.

            UNTRACKED       UNMODIFIED           MODIFIED           STAGED
                |                 |                 |                 |
                |   add the file  |  edit the file  | stage the file  |
                |---------------->|---------------->|---------------->|
                |                 |                 |                 |
                | remove the file |               commit              |
                |<----------------|<----------------------------------|

        Essential Commands:
            -> git init: create a repository

            -> git add: add the file to the stage version

            -> git diff: shows the modifications of a not added file
                -> git diff --name-only: shows only the names of the modified files

            -> git checkout <file>: resets the last modification shown by git diff on "file" (only works if it's not added)

            -> git reset HEAD <file>: unstage a file

            -> git commit -m "<message>": commit the file to the Git's branch with a message

            -> git commit -am "<message>": commit ALL the files to the Git's branch with a message

            -> git log --decorate: shows the log of commits with all information
                -> git log --graph: show the log with a graphic format

            -> git shortlog: shows the log of commits with less information

            -> git show <lognumber>: shows the details of a certain commit

            -> git reset --<mode> <lognumber>: resets the commit with different properties depending on the reset mode.
                -> git reset --soft <lognumber>: resets a commit, but it's still in the stage area, it's ready to commit again
                -> git reset --mixed <lognumber>: resets a commit, and removes the file from the stage area (it's now modified)
                -> git reset --hard <lognumber>: resets a commit and all the changes made before you added it (careful with this one)

        SECTION 4: Remote Repositories

            -> git push origin main: pushes the fixed branch origin to the remote branch main

            -> g clone <sshaddres> <name>: clones the remote repository with address "sshaddres" to a repository "name"

        SECTION 5: Git Branches

            -> git branch: show all the branches and which one you are in at the moment
                -> git branch -D <branchname>: deletes the branch named "branchname"

            -> git checkout -b <branchname>: create another branch named "branchname" and switches to it

            -> git checkout <branchname>: just switches to the branch named "branchname"

            TWO TYPES OF BRANCHES FLOW CONTROL:

                -> git merge <branch>: create another commit to show that the differente branches were put together again

                    -> Advantage: maintains the history of the rebranch
                    -> Disadvantage: create a "useless" commit

                -> git rebase <branch>: move the pointer of the new branch to the main one, "deleting" the new

                    -> Advantage: keeps the commits in a linear history
                    -> Disadvantage: loses the information of the rebranching

        SECTION 6: Extras

            -> .gitignore: file that states which files or type of files you don't want git to track
                -> <filename.type>: ignores the specific file
                -> *<.type>: ignores all files from the type specified

            -> git stash: hides the modifications of files for you to deal with them later
                -> git stash apply: apply the modifications you've hidden
                -> git stash list: show all the modifications hidden
                -> git stash clear: clear all the modifications hidden

            -> Alias: enable you to create shortcuts for git commands
                -> example: "git config --global alias.s status" enable you to do "git status" with just "git s"

            -> Tags Versioning: use tags to categorize your repository by big changes you made
                -> git tag -a <version> -m "<message>"
                -> version must be of the type '1.0.0', '1.0.1', etc
                -> when you push your repository to the remote repository, it will show the tag on the release menu of github

            -> git revert <lognumber>: contrary to git reset, it doesn't erase the modifications on the files of the commit. Instead, it creates another commit that show which changes you'd want to revert and shows a "-<changes" on git show <lognumber>
                -> tip: great to use when you don't have much time to deal with your project, or to not erase all changes

            -> how to erase flags and branches from the remote repository?
                -> "git push origin :<tagnumber>"
                -> "git push origin :<branchname>"

        SECTION 7: Git Main Flags

            -> -m: passes a message

            -> -d: delete anything you want
                -> example: git tag -d <tagname>
