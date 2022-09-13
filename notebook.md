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

            -> git shortlog: shows the log of commits with less information

            -> git show <lognumber>: shows the details of a certain commit

            -> git reset --<mode> <lognumber>: resets the commit with different properties depending on the reset mode.
                -> git reset --soft <lognumber>: resets a commit, but it's still in the stage area, it's ready to commit again
                -> git reset --mixed <lognumber>: resets a commit, and removes the file from the stage area (it's now modified)
                -> git reset --hard <lognumber>: resets a commit and all the changes made before you added it (careful with this one)
