# Git
`Git` `Code versioning` `Github`

Git is a version control system widely used in present day development.

## Resources

- [Resources to learn Git](https://docs.github.com/en/get-started/git-basics/set-up-git)
- [About READMEs](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-readmes)
- [How to write a Git commit message](https://cbea.ms/git-commit/)
- [Learning branching](https://learngitbranching.js.org/)
- [Effective pull requests and other good practices for teams using GitHub](https://codeinthehole.com/tips/pull-requests-and-other-good-practices-for-teams-using-github/)

## Learning Objectives

- What is source code management
- What is Git
- What is GitHub
- What is the difference between Git and GitHub
- How to create a repository
- What is a README
- How to write good READMEs
- How to commit
- How to write helpful commit messages
- How to push code
- How to pull updates
- How to create a branch
- How to merge branches
- How to work as collaborators on a project
- Which files should and which files should not appear in your repo

At the end of this project you should be able to reproduce and understand these command lines:

```
$ git clone <repo>
$ touch test
$ git add test
$ git commit -m "Initial commit"
$ git push origin main
```

## Tasks

### Task 0

Create and set up your Git and GitHub account.

You will need a GitHub account for majority of your projects as a Software Engineer.

1. Step 0 - Create an account on GitHub [if you do not have one already], to create a new GitHub
account for free visit [here](https://github.com/).

2. Step 1 - Create a Personal Access Token on Github.  

    To have access to your repositories and authenticate yourself, you need to create a Personal Access Token on Github.

    You can follow [this tutorial](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens) to create a token.

3. Step 3 - Create your first repository
Using the graphic interface on the [github website](https://github.com/), create your first repository.

    - Name: `alx-pre_course`  
    - Description: "I'm now a ALX Student, this is my first repository as a full-stack engineer"
    - Public repo
    - No `README`, `.gitignore`, or license

4. Step 4 - Open your terminal and Clone your repository  
On your terminal do the following:
- Clone the repository
    ```
    root@896cf839cf9a:/# git clone https://{YOUR_PERSONAL_TOKEN}@github.com/{YOUR_USERNAME}/alx-pre_course.git
    Cloning into 'alx-pre_course'...
    warning: You appear to have cloned an empty repository.
    ```
*Replace {YOUR_PERSONAL_TOKEN} with your token from step 1*  
*Replace {YOUR_USERNAME} with your username from step 0 and 1*

5. Step 5 - Create the `README.md` and push the modifications

- Navigate to this new directory. [Tips](https://askubuntu.com/questions/232442/how-do-i-navigate-between-directories-in-terminal)
    ```
    root@896cf839cf9a:/# cd alx-pre_course/
    root@896cf839cf9a:/alx-pre_course#
    ```

- Create the file `README.md` with the content `My first readme`. [Tips](https://forum.howtoforge.com/threads/echo-into-a-file.115/)
    ```
    root@896cf839cf9a:/alx-pre_course# echo 'My first readme' > README.md
    root@896cf839cf9a:/alx-pre_course# cat README.md
    My first readme
    ```

- Update your git identity
    ```
    root@896cf839cf9a:/alx-pre_course# git config --global user.email "you@example.com"
    root@896cf839cf9a:/alx-pre_course# git config --global user.name "Your Name"
    ```

- Add this new file to git, commit the change with this message “My first commit” and push to the remote server / origin
    You can now check your repository on GitHub to see if everything is good.
    ```
    root@896cf839cf9a:/alx-pre_course# git add .
    root@896cf839cf9a:/alx-pre_course# git commit -m 'My first commit'
    [master (root-commit) 98eef93] My first commit
     1 file changed, 1 insertion(+)
     create mode 100644 README.md
    root@896cf839cf9a:/alx-pre_course# git push
    Enumerating objects: 3, done.
    Counting objects: 100% (3/3), done.
    Writing objects: 100% (3/3), 212 bytes | 212.00 KiB/s, done.
    Total 3 (delta 0), reused 0 (delta 0)
    To https://github.com/{YOUR_USERNAME}/alx-pre_course.git
     * [new branch]      master -> master
    ```

Repo :
- GitHub repository: `alx-pre_course`
- File: `README.md`

***

### Task 1

Create a new directory called `0x01-git` in your `alx-pre_course` repo.  
Make sure you include a non empty `README.md` in your directory:
- At the root of your repository `alx-pre_course`
- And in the directory `0x01-git`  

Repo :
- GitHub repository: alx-pre_course

***

### Task 2

For the moment we have an empty project directory containing only a README.md. It’s time to code!

Inside 0x01-git:

- Create these directories at the root of your project: `bash`, `c`, `js`
- Create these empty files:
    - `c/c_is_fun.c`
    - `js/main.js`
    - `js/index.js`
- Create a file `bash/alx` with these two lines inside: `#!/bin/bash` and `echo "ALX"`
- Create a file bash/school with these two lines inside: `#!/bin/bash` and `echo "School"`
- Add all these new files to git
- Commit your changes (message: “Starting to code today, so cool”) and push to the remote server

Repo :
- GitHub repository: `alx-pre_course`
- Directory: `0x01-git`
- File: `bash/alx`, `bash/school`, `c/c_is_fun.c`, `js/main.js`, `js/index.js`

***

### Task 3

A branch is like a copy of your project. It’s used mainly for:

- adding a feature in development
- collaborating on the same project with other developers
- not breaking your entire repository
- not upsetting your co-workers

The purpose of a branch is to isolate your work from the main code base of your project and/or from your co-workers’ work.

For this project, create a branch update_script and in this branch:

- Create an empty file named `bash/98`
- Update `bash/alx` by replacing `echo "ALX"` with `echo "ALX School"`
- Update `bash/school` by replacing `echo "School"` with `echo "The school is open!"`
- Add and commit these changes (message: “My personal work”)
- Push this new branch [Tips](https://docs.github.com/en/get-started/using-git/pushing-commits-to-a-remote-repository)
  
Perfect! You did an amazing update in your project and it’s isolated correctly from the main branch.

Ho wait, your manager needs a quick fix in your project and it needs to be deployed now:

- Change branch to `main`
- Update the file `bash/alx` by replacing `echo "ALX" `with `echo "ALX School is so cool!"`
- Delete the directory `js`
- Commit your changes (message: “Hot fix”) and push to the origin  

Vuala!!, hot fix is done!

Repo:
- GitHub repository: `alx-pre_course`
- Directory: `0x01-git`
- File: `bash/alx`, `bash/school`, `bash/98`

***

### Task 4

Of course, you can also work on the same branch as your co-workers and it’s best if you keep up to date with their changes.

For this task – and only for this task – please update your file `README.md` in the main branch from GitHub.com. It’s the only time you are allowed to update and commit from GitHub interface.

After you have done that, in your terminal:

- Get all changes of the main branch locally (i.e. your `README.md` file will be updated)
- Create a new file `up_to_date` at the root of your directory and in it, write the git command line used
- Add `up_to_date` to git, commit (message: “How to be up to date in git”), and push to the origin

Repo:
- GitHub repository: `alx-pre_course`
- Directory: `0x01-git`
- File: `README.md`, `up_to_date`

***

### Task 5

Collaboration is cool, but not really when you update the same file at the same time…

To illustrate that, please merge the branch `update_script` to `main`: “Cool, all my changes will be now part of the main branch, ready to be deployed!”

**HHHHHHHAAAAAAAA**

```
CONFLICT (content): Merge conflict in bash/alx
```

As you can see, you have conflicts between two branches on the same file.

Your goal now is to resolve conflicts by using the version of the branch `update_script`, and push the result to the origin.

At the end, you should have all your work from the branch `update_script` (new file and two updated files) and all latest `main` commits (new files, delete folder, etc.), without conflicts.

Repo:
- GitHub repository: `alx-pre_course`
- Directory: `0x01-git`

***

### Task 6

Create a `.gitignore` file and define a rule to never push `~` files (generated by Emacs). [Tips](https://git-scm.com/docs/gitignore)

Repo:
- GitHub repository: `alx-pre_course`
- Directory: `0x01-git`
- File: `.gitignore`
