First thing's first, run:

    $ man git

"git - the stupid content tracker"
Wait what? 

### Intro to Git.

Git is a *source code management* tool that implements *merge based* revisioning and optimizes for *speed*.
Git stores every single version branch as compressed diffs, allowing almost every command to be performed locally.

Let's dive right in.
Make a new directory and cd into it. Then run

    $ git init
    $ ls -a
    .  ..  .git
    
That .git directory is what lets git know it can go to town. Otherwise git will complain that you're not in a git repository.

Grab a group of 3-4 people and introduce yourselves! Now we're going to have your repositories introduce themselves.
Go to https://github.com and make an account. Then elect a leader to create a public repository and add the members of the group to the account.

The leader should then create a file called `introductions.py in the git directory.

To tell git to track a file use

    $ git add <filename>

Once you've added all the files you want in your project (this is called staging), you should `commit them

    $ git commit -m "<This string tells you about what changes were made in the commit.>"

Write a python function that prints an introduction:

    def introduce():
        print "Hi! I'm Git."


