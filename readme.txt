$ git add                     Add file contents to the index

$ git am                      Apply a series of patches from a mailbox
# to  apply we use command
$ git am <patch-file>
# to resolve conflits and continue, we use
$ git am --continue
# to skip the procees of applying the patch file, we use
$ git am --skip
# to stop the process of the patch file application, We use
$ git am --abort

$ git archive                 Create an archive of files from a named tree
# By default "git archive" command only uses the tracked files and excludes the untracked files. 
# If you need to archieve a file which is in Zip format an dlatest changes from the latest commit of zip file, then we use 
$ git archive --format=zip -o latest.zip HEAD
# If we need to create n archieve from a particular or specific commit, then we use
$ git archive --format=tar.gz -o archive.tar.gz <commit-hash>(general command)
# suppose If we need to create an archive from a specific branch, then we use
$ git archive --format=zip -o branch.zip <branch-name>
#If you need to archive only specific files or directories, then we use 
$ git archive --format=zip -o subset.zip HEAD path/to/file1 path/to/dir1
# If we need to archive main branch into the main.zio files
$ git archive --format=zip -o main.zip main
$ git push --set-upstream origin master
It is used to push the code from local repository to the remote repository

$ git bisect                  Use binary search to find the commit that introduced a bug
# It is command used to search a bug within the commits that we made. It is used to find
 the bugs between the bad commit and the good commits. so we use
 $ git bisect start
 $ git bisect bad <bad-commit> (commit with bugs, If the bug is present mark it as)
 $ git bisect good <good-commit> (commit without bugs, if the bug is not present mark it as)
 # note: If you do not specify <bad-commit> and <Good-commit>, git will take the current commit as bad
 once Git identifies the bad commit we can end the bisect session by using command below
 $ git bisect reset
 $ git bisect start
 $ git bisect bad HEAD
 $ git bisect good <commit-hash>
 $ git bisect run <script-name>

$ git branch                  List, create, or delete branches
# Generally we use commands below
$ git branch -a (to List the branches of both local and remote )
$ git branch <branch-name> (to create new branch)
$ git checkout -b <branch-name>/git switch -c <branch-name> (to create and switch the branch)
$ git switch <branch-name>/ git checkout <branch-name>(to switch the current branch into the another branch)
$ git branch -m <new-branch-name> ( to rename the current branch)
$ git branch -m <old-branch-name> <new-branch-name>
$ git branch -d <branch-name> (to delete the brnach only if it is merged with other branch)
$ git branch -D <branch-name> (to forcefully delete the branch eventhough it is not merged)
$ git branch feature-<branch-name>/ git checkout feature-<branch-name>/git checkout -b feature-<branch-name>( to create a new feature branch)
$ git checkout main &&-> git merge feature-<branch-name>( to switch back from feature to main branch and merge the feature branch changes)
$ git branch -r ( to see the remote branch)
$ git checkout -b <local-branch-name> origin/<remote-branch-name> (to create local branch tracking the remote branch)

$ git bundle                  Move objects and refs by archive
# it is used to create a single file of git repo and to transfer the file to other location/ shared with someone else.
$ git bundle create <file.bundle> <branch-name> ( to create the bundle files that creates all the commits)
$ git bundle create repo.bundle main (to create the repo.bundle file that conatains all the commits from the main branch)
$ git bundle create <file.bundle> <start-commit>..<end-commit> (we can bundle only a specific range of commitss by spcifying the range)
$ git bundle create repo.bundle HEAD~10..HEAD (to create a repo.bundle file containing the last 10 commits)
$ git bundle create <file.bundle> --all/ git bundle create repo.bundle --all(to include all references(branches, tags etc..,)in the bundle)
$ git bundle verify <file.bundle> (To verify the bundle file whether it is valid or not)
$ git clone <file.bundle> <directory> (to clone the bundle file)
$ git fetch <file.bundle> <ref> (To fetch from a bundle file into Existing repo)
$ git pull <file.bundle> <branch-name> (to apply the contents of the bundle to our repository, the we use)

$ git checkout                Switch branches or restore working tree files
$ git cherry-pick             Apply the changes introduced by some existing commits
$ git citool                  Graphical alternative to git-commit
$ git clean                   Remove untracked files from the working tree
$ git clone                   Clone a repository into a new directory
$ git commit                  Record changes to the repository
$ git describe                Give an object a human readable name based on an available ref
$ git diff                    Show changes between commits, commit and working tree, etc
$ git fetch                   Download objects and refs from another repository
$ git format-patch            Prepare patches for e-mail submission
$ git gc                      Cleanup unnecessary files and optimize the local repository
$ git gitk                    The Git repository browser
$ git grep                    Print lines matching a pattern
$ git gui                     A portable graphical interface to Git
$ git init                    Create an empty Git repository or reinitialize an existing one
$ git log                     Show commit logs
$ git maintenance             Run tasks to optimize Git repository data
$ git merge                   Join two or more development histories together
$ git mv                      Move or rename a file, a directory, or a symlink
$ git notes                   Add or inspect object notes
$ git pull                    Fetch from and integrate with another repository or a local branch
$ git push                    Update remote refs along with associated objects
$ git range-diff              Compare two commit ranges (e.g. two versions of a branch)
$ git rebase                  Reapply commits on top of another base tip
$ git reset                   Reset current HEAD to the specified state
$ git restore                 Restore working tree files
$ git revert                  Revert some existing commits
$ git rm                      Remove files from the working tree and from the index
$ git scalar                  A tool for managing large Git repositories
$ git shortlog                Summarize 'git log' output
$ git show                    Show various types of objects
$ git sparse-checkout         Reduce your working tree to a subset of tracked files
$ git stash                   Stash the changes in a dirty working directory away
$ git status                  Show the working tree status
$ git submodule               Initialize, update or inspect submodules
$ git switch                  Switch branches
$ git tag                     Create, list, delete or verify a tag object signed with GPG
4 git worktree                Manage multiple working trees

$ git pull : It is combination of fetch and merge. It is used to pull the changes from the remote repository to the local repository.
$ git merge: It is used to merge the changes in current branch to the specified branch.
$ git fetch: It is used to fetch the changes that has been made. It is used to fetch the history of the changes.
