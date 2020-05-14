# UCL Data Science Society - Internal Training 1: Introduction to _Git/Github_

## Credit

Created by Zhaoxuan "Tony" Wu, Head of Science, *UCL Data Science Society*

[See me on _Github_🙋‍♂️](https://github.com/TonyWu3027)

## Prerequisition

-   [ ] Setup a _Github_ account
-   [ ] For _MacOS_/_Linux_: Download _Git_
-   [ ] For _Windows_: Download _Bash_

### _Git_

You should download [_Git_](https://git-scm.com/downloads). Feel free to check the [_official documentation_](https://git-scm.com/docs) if you are interested in. We will be using the _Terminal_, so it might be helpful to get familiar with the commands. 

Recommended Terminal for MacOS: _iTerm2_ 

Recommended multi-lang IDE: _Atom_, _Visual Studio_, _Sublime Text_, or _Vim_, which is pre-installed on MacOS

### _Github_

Get yourself a _Github_ account, it's free! If you prefer graphical interface, [_Github Desktop_](https://desktop.github.com). But we are going to learn _Git_ and _Github_ using command line today. Also, remember to claim your [_Github Student Package_:package:](https://education.github.com/pack)

## What is _Git_, and Why?

>   *Git is a [free and open source](https://git-scm.com/about/free-and-open-source) **distributed version control system** designed to handle everything from small to very large projects with speed and efficiency.* 

-   Industrial production standard
-   Hackathon
-   Writing a book
-   Keeping lecture notes
-   ...

## How is it different from _Github_?

_Git_ is a ***system*** that manages the version control of a project, while _Github_ is a ***remote platform*** that hosts that project using _Git_. For instance: `git push` uploads your current local repository to _Github_

## Relationship

![A Simplied Git/Github Model](./assets/figure1.png)

>   ***Repository*** ("Repo") : a receptacle or place where things are deposited or stored

## Your first _Git_ repo

Do the following on your own _Terminal_

### Initialisation of project

Create a _directory_ (or better known as ***"folder"***) for your project:

```bash
mkdir my-novel
```

Go to that _directory_:

```bash
cd my-novel
```

Initialise the project with _Git_ so that _Git_ manages the version control of the project:

```bash
git init
```

Now you should have a `.git` folder in your directory, which is invisible currently. Also, your current project  is called the _local workspace_.

### Write something

Let's write a ***novel*** together! 

>   You can do it with your IDE or with command line. 

Create  `intro.md`:

```bash
touch intro.md
```

Edit the file using the built-in editor **_Vim_**, or use ***IDE***. Copy and paste the following text:

```markdown
It was the best of times, it was the worst of times; it was the age of wisdom, it was the age of foolishness; it was the epoch of belief, it was the epoch of incredulity; it was the season of light, it was the season of darkness; it was the spring of hope, it was the winter of despair; we had everything before us, we had nothing before us; we were all going direct to Heaven, we were all going direct the other way.
```

### Stage the changes

Before you commit your changes, you should _add_ your changes to the stage, or "_stage_" it.

```bash
git add intro.md 
```

>   ***Note that***: `git add` takes in a parameter, which is the filename. The *"wildcard"* mode is also available: it stages ***every*** file that has been changed. To do so, execute: `git add .` to pass `.` as a wildcard parameter

 To check your _stage_:  

```bash
git status
```

And you will see:

```shell
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)

	new file:   intro.md
```

>   ***Note that***: here we can see some important information
>
>   -   Branch: `master` (stay tuned for what it means)
>   -   Commits: none (stay tuned for what it means)
>   -   Changes: `new file: intro.md` - `intro.md` is staged and is ready to be commited

### Commit the changes

Now, commit your changes:

```bash
git commit -m "Initialise project with a intro"
```

>   ***Note that***: `git commit` takes in commit comment using the `-m` flag,  followed by your comment string. It can be anything. Here we use `"Initialise project with a intro"` as example, which is usually what you do for your first commit literally

Congrats! 🥳 You just commited your first contribution to the project! Now this version of commit is officially in your _local repository_ (_**local repo**_). 

## Branching: the magical bit of _Git_

When we develop a project, we tend to create a branch for the stuff we are working on here. For instance, in a collaborative working environment of a **webpage**, somebody will take care of the **frontend** while others will be working with the **backend**, or a team will be responsible for the ***styling***, and the rest will write **unit tests**. So in this specific project, we can ***branch*** our project into a few branches:

-   `frontend`
-   `backend`
-   `unit-test`
-   ...

and they can start working simultaneously. For instance: a frontend engineer can start writing JavaScripts while the backend scripting is not finished. Other good thing about branching is that it makes sure your commits do not *"contaminate"* your `master` branch (the default/major branch) before its ready.

### Chapter 1

Create and switch to branch `chapter-1`:

```shell
git checkout -b chapter-1
```

>   Note that:
>
>   `-b` flag accepts a parameter `<branch_name>` and create such a branch which is not existed yet. Switching to an existing branch does not require `-b` flag

Create `ch-1.md` and write in the following:

``` markdown
In 1775, a man flags down the nightly mail-coach on its route from London to Dover. The man is Jerry Cruncher, an employee of Tellson's Bank in London; he carries a message for Jarvis Lorry, a passenger and one of the bank's managers. Lorry sends Jerry back to deliver a cryptic response to the bank: "Recalled to Life." The message refers to Alexandre Manette, a French physician who has been released from the Bastille after an 18-year imprisonment. Once Lorry arrives in Dover, he meets Dr. Manette's daughter Lucie and her governess, Miss Pross. Lucie has believed her father to be dead, and faints at the news that he is alive; Lorry takes her to France to reunite with her father.

In the Paris neighbourhood of the Faubourg Saint-Antoine, Dr. Manette has been given lodgings by his former servant Ernest Defarge and his wife Therese, owners of a wine shop. Lorry and Lucie find him in a small garret, where he spends much of his time making shoes – a skill he learned in prison – which he uses to distract himself from his thoughts and which has become an obsession for him. He does not recognise Lucie at first but does eventually see the resemblance to her mother through her blue eyes and long golden hair, a strand of which he found on his sleeve when he was imprisoned. Lorry and Lucie take him back to England.
```

Add and commit

### Chapter 2

Create and switch to branch `chapter-2`

Create `ch-2.md` and write something:

```markdown
> Side notes: I don't know what to write but there should be a chapter 2, any thought?
```

Add and commit

### Write a bit more for _Intro_

Add the following to `intro.md`

```markdown
> Side notes: Damn that's a good intro
```

Add and commit

### Commit history

```shell
git log 
```

>   ***Note that***: here are some useful flags:
>
>   -   `--oneline`: show each _commit_ in one line: `<hash> <commit_msg>`
>
>   -   `--graph`: visualisation of the commit history
>   -   `--all`: show the history across all branches
>
>   To quit the log, press `<q>`

### Put them together

Go to `master` branch

```shell
git checkout master
```

Merge with `chapter-1`

```shell
git merge chapter-1
```

Same for `chapter-2`

## Security, security, security, and `.gitignore`

You might notice that it is quite dangerous to commit a copy of your sensitive information to a _repo_ or to a _remote repo_. 

-   API keys
-   Database password
-   Credentials 
-   Biometrics data
-   Data under NDA
-   `.DS_Store`
-   `/node_modules`
-   ...

### My little secret

At `master`, create `secret.md` and write:

```markdown
> Don't tell anyone:
I copied those chapters from the Wikipedia page of "A Tale of Two Cities". Don't tell anyone, otherwise my careers is ****ed. Hope they don't do turnitin here
```

### `.gitignore`

By using `.gitignore`, you can prevent certain files to be commited to a _repo_

```bash
touch .gitignore
```

Directly add the name of the files you want to hide to that `.gitignore` file:

```bash
.DS_Store
secret.md
```

Now, _stage_ and _commit_ everything and see what happen.

>   *And here comes a real story about poor Leo and his crypto-currency tokens...*

## Ah Damn... I want to go back a bit

Assume you did something wrong but you committed it, and you don't want to commit a debugged version of it for some reason (like it will look stupid in your commit history), you might want to ***remove*** some commits from the history.

For instance, going back to the last commit:

```shell
git reset --soft HEAD^
```

>   ***Note that***:
>
>   `git reset` has several ***modes***(`--soft`, `--hard` and `--mixed`) and there are ways to manipulate the pointer to point at a commit that is higher up in the tree, using `^` and `~`. Please refer to the [doc](https://git-scm.com/docs/git-reset)

## Enough for _Git_, how about some _GitHub_: Remote _repo_

Now you might want to ***share*** your code with other developer, you can do this by putting your project on a remote repo. Do this by call the following function:

```python
You.watch(Tony.live_demo("How to use GitHub"))
```

## Collaborative Coding 101

### If that's not your own project

 ***Obtain the repo***

-   Fork an existing project
-   Clone the _your remote repo_ to local

***Make changes***

-   Make changes to _local repo_
-   Add _remote forked repo_ to `remote`:

```bash
git remote -v
git remote add upstream <upstream_url>
```

***Push to remote***

-   `push` to _your remote repo_
-   Make a pull request

***Sync with forked repo***

**EITHER**

-   Keep your local _repo_ synced with the _remote forked repo_ and push to _your remote repo_

```bash
git fetch upstream
git merge upstream/master
git push -u origin upstream
```

**OR**

-   Sync _your remote repo_ to _remote forked repo_ on _Github_
-   `pull`  from _your remote repo_ to keep _your local repo_ synced

### *If that's your own project*

-   Manage pull request
-   Review changes, make comments, reject or `merge` pull request

## Practice: Signing an attendance sheet

Let's sign an attendance sheet collaboratively!

[The repo to the attendance sheet](https://github.com/TonyWu3027/attendance-sheet/blob/master/README.md)

### BONUS: Git Internals

If we've got time, execute the following code for learning **_Git_ *internals***

```java
import ucl.dss.science.Tony;

public class GitDemo {
     public static void main(String[] args) {
          Tony.present(Git.internals);
     }
}
```

## To Wrap Up

_Git/Github_ is massive, I haven't figure out all of it as well. This is a brief introduction to the tip of this iceberg.

[Official Documentation :bookmark_tabs:](https://git-scm.com/docs)

## One More Thing...

***Stay tuned*** for everything about data science

[Subscribe to our offical IG if you haven't do so :ballot_box_with_check:](https://www.instagram.com/ucl.datasci/)

And [our FB! :champagne: ](https://www.facebook.com/ucldata/)

And follow [me on GitHub](https://www.github.com/TonyWu3027)



