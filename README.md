First thing's first, run:

        $ man git

"git - the stupid content tracker"
Wait what? 

### Intro to Git.

Git is a <em>source code management</em> tool that implements <em>merge based</em> revisioning and optimizes for <em>speed</em>.
Git stores every single version and branched into compressed blobs, allowing almost every command to be performed locally.


You're downstream of the remote because data is passed down (downloaded) to you. The remote is upstream.
When you push, git needs to know which upstream you're pushing to, so set it with
$ git push -u origin master
Clone automatically sets the remote you cloned from as the upstream.

Branches, HEAD, and commits just *point* to particular commits. Commits also *point* to their parent commits (multiple if merged.

git config --global merge-conflictstyle diff3

Initialization
git init

Remote
git remote add
git fetch

Branching
git checkout (-b)
git merge (bring the target branch in)
git rebase (rebase out to the target branch)

Staging
git status
git diff
git add
git rm
git reset (moves a branch to a specified commit)
git revert (plops the parent commit of the target down as a new branch under HEAD)

Committing
git commit (-m)
git log

Pushing (Yesss feels so good)
git push

Issues
