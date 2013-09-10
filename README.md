First thing's first, run:

    $ man git

"git - the stupid content tracker"
Wait what? 

### Intro to Git.

Git is a *source code management* tool that implements *merge based* revisioning and optimizes for *speed*.
Git stores every single version and branched into compressed blobs, allowing almost every command to be performed locally.

Make a new directory and cd into it. Then run

    $ git init
    $ ls -a
    .  ..  .git
    
That .git directory is what lets git know it can go to town. Otherwise git will complain that you're not in a git repository.

Grab a group of 3-4 people and introduce yourselves! Now we're going to have your repositories introduce themselves.
Go to https://github.com and make an account. Then elect a leader to create a public repository and add the members of the group to the account.



Write a python function that prints an introduction:

    def introduce():
        print "Hi! I'm Git."


