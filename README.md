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

Leader >>> You should then create an empty file called `introductions.py` in the git directory by using this command:

    $ touch introductions.py

To tell git to track a file use

    $ git add <filename>

(PROTIP: You can run `$ git status` to figure out what files you've changed and which ones you've already added.)

Once you've added all the files you want in your project (this is called staging), you should `commit them and then push the file to github:

    $ git commit -m "<This string tells you about what changes were made in the commit.>"
    $ git push

Group >>> Run 

    $ git pull

Ta-da! The new `introductions.py` file is now on your local machine.
Open up that `introductions.py` and write a python function that prints an introduction of yourself:

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

That means the remote repository was a commit or two ahead of yours thanks to your teammates successfully pushing their code before you.

To fix this, do:

    $ git pull

which will bring your teammates' changes from the remote repo to your local machine. Since you've committed your local changes beforehand,
git is going to ask you to write a commit message for the merge. 

You'll probably see a message like this

    $ git pull
    Auto-merging introductions.py
    CONFLICT (content): Merge conflict in introductions.py
    Automatic merge failed; fix conflicts and then commit the result.

Oh noes! Open up the `introductions.py` and you'll see something like:    

    <<<<<<< HEAD
    def introduce():
        print "Hi! I'm Fred."
    =======
    def introduce():
        print "Hi! I'm George."
    >>>>>>> [really long string of letters and numbers]

You now have to manually resolve these conflicts, for example:

    def introduceFred():
        print "Hi! I'm Fred."
    
    def introduceGeorge():
        print "Hi! I'm George."

Now do ye olde add-commit-push sequence again and all should be well.

Leader >>> Once everybody has collected their `introduceName()` functions and pushed up to the repositories, add these lines at the bottom.

    def main():
        introducePersonA()
        introducePersonB()
        introducePersonC()

    if __name__ == "__main__":
        main()

Basically, write a function `main()` that calls the introduce functions for everybody in your group, then add that last if statement at the bottom that calls `main()`.

If you run

    $ python introductions.py
    "Hi my name is Ron!"
    "Hi my name is Ginny!"
    "Hi my name is Fred!"
    "Hi my name is George!"

your program will introduce everybody. Hurray! Now add-commit-push it up to github so your entire group can `git pull` and enjoy your finished project.

--------------------------------

Best Practices:

- Write a descriptive commit message.
- Break up commits into small changes.
- Make master clean. Work on your own local branch and merge changes into master when you know they work.
- Add your SSH key to github so you don't have to type in your user/pass every time.
- git checkout [filename] to restore it to the state of the latest commit.
- http://git-scm.com/book/en/Getting-Started-First-Time-Git-Setup Set up git properly the first time.
