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
Go to https://github.com and make an account. Then choose a leader for the group.

To the leader >>> create a new repository on github and initialize it with a README. Add your underlings as collaborators to the repository.

To the entire group >>> Clone your brand new github repository:

    $ git clone https://github.com/[your-leader's-username]/[your-repository-name.git]

Leader >>> You should then create an empty file called `introductions.py in the git directory by using this command:

    $ touch introductions.py

To tell git to track a file use

    $ git add <filename>

Once you've added all the files you want in your project (this is called staging), you should `commit them and then push the file to github:

    $ git commit -m "<This string tells you about what changes were made in the commit.>"
    $ git push

Group >>> Run 

    $ git pull

Ta-da! The new `introductions.py file is now on your local machine.
Open up that `introductions.py and write a python function that prints an introduction of yourself:

    def introduce():
        print "Hi! I'm Git."

and then do the same add-commit-push from earlier:

    $ git add introductions.py
    $ git commit -m "<Describe the changes you just made.>"
    $ git push

If you weren't the first guy to push, you probably got something like:

    $ git push
    To https://github.com/[your-leader's-username]/[your-repository-name.git]
     ! [rejected]        master -> master (non-fast-forward)
    ...
