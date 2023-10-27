# GIT

[Home][Home]

## How To Git Gud

# Readme

## Git

### Installation

> Step 0: Install Git and Create a GitHub Account

#### Step 1: Create a Local Git Repository

```zsh
cd ~/Desktop
mkdir newProject
cd newProject
git init
git remote add remoteName https://github.com/Jim20220214/newProject.git
git branch -M branchName
echo "# Readme" >> readme.md
git add readme.md
git commit -m "first commit"
git push -u remoteName branchName
git status
```

#### Step 2: Create a New Repository on GitHub
```zsh
git remote add [remoteName] [branchURL]
git branch -M [branchName]
```

#### Step 3: Add a File to the Repository
`git add [filename]`
>You can check which files Git is tracking by running: `git status`



#### Step 4: Unstage Files from Git
`git reset -- [file_path]`  
` git rm --cached [file-name]`

<p class="" style="page-break-before: always"></p>

#### Step 5: Create a Commit
`git commit -m "Notes about the commit"`

#### Step 6: Undo Last Commit
`git revert [hash]`

>Get the hash from the commit by checking the log: `git log`

#### Step 7: Create a New Branch
1. Create branch
`git branch [new_branch_name]` (May use -b or -B, RTFM)
2. Switch branch
`git checkout [branch_name]`
3. Set Upstream
`git push -u [remote] [branch]`

#### Step 8: Switch Branches

`git checkout [branch_name]`

#### Step 9: Rename a Local or Remote Git Branch

`git branch -m new-name`

>Since there isn’t a way to directly rename a remote Git branch, you first need to delete the old branch name, then push the new branch name to the remote repository.

#### Step 10: Delete a Local or Remote Git Branch

Deleting a local branch doesn't affect a remote branch. To delete a local Git branch, run:

`git branch -d [branch_name]`

Use the following syntax to delete a remote Git branch:

`git push [remote] --delete [branch_name]`


`git branch` - Lists Local branches
`git branch -r` - Lists Remote branches


#### Step 12: Set Upstream Branch
Sending something upstream in Git means that you are sending it back to the repository owner.

Using the git set upstream command, you can choose the flow direction of your current local branch. The command also allows you to change the default remote branch.

`git push -u [remote] [branch]`

you can use this new config entry to automatically setup remote tracking:
`git config --global push.autoSetupRemote true`

#### Step 13: Remove a Git Remote

`git remote remove [remote name]`

>`git remote -v` shows the available remotes

#### Step 14: Git Merge

1. Create a branch 
    1. Create `git checkout -b [branch name]`
    2. Configure upstream `git push -u [remote] [branch]` 
    3. Add `git add readme.md`
    4. Commit `git commit -m "message text"`
    5. Push `git push [remote-name] [branch-name]`
2. To merege we want to be on the "main" branch that will get the branch merged in to it.
    1. Make sure we are on the right branch `git status`
    2. Otherwise `git checkout [main-branch]`
    3. Update the main branch with `git fetch` and `git pull`
    4. Merge `git merge [branch-name]`
3. Clean up by removing the branch localy remotely and finaly prune our remote to reflect only existing branches
    1. Local `git branch -d [branchToDelete]`
    2. Remote `git push [remote] -d [branchToDelete]` and `git branch -d -r [remote/branchToDelete]`

> [!NOTE]
> Prune can be usefull if not all branches are reflected correctly  
> `git remote prune [remote]` or `git fetch -p` `git pull -p`

#### Step 15: Resolve Merge Conflicts

Nothing to say origin

#### Step 16: Create a Pull Request
Create a pull request (PR) to inform a repository owner that they should review the changes you've made to their code. Then the owner can approve the pull request and merge the changes into the main repository.

If you are the co-owner or owner of a repository, you don't have to create pull requests to merge your changes. However, you can still do it to keep track of your feature updates and history.

For this guide, we will create a readme file for our repository locally and make a pull request on GitHub to illustrate the process.

1. Pull request
    1. Create `git checkout -b [branch name]`
    2. Configure upstream `git push -u [remote] [branch]` 
    3. Add `git add readme.md`.
    4. Commit `git commit -m "Added a readme file"`
    5. Push `git push [remote] [branch name]`

2. Log in to your GitHub page. There is now a Create pull request option in your repository with the branch name we created in the command line. Click the Compare & pull request button.
    1. GitHub states if you can merge the branches and apply the changes. Optionally, add a comment about your pull request and click Create pull request.

    2. You can accept the changes in the Pull requests tab on GitHub. When you merge the branches, delete the obsolete branch by clicking Delete branch to keep the repository clean.


#### Step 17: Synchronize Changes on GitHub and Locally
When you merge changes on GitHub, they don't appear automatically in your local repository. You have to pull the changes to your local repository to see the updates.

Synchronize your local repository with GitHub by running:

`git pull [remote] [branch]`


----

`#0969DA`

----


`git remote add <remote-name> <remote-repo-URL>`
git commit -a --allow-empty-message -m ""

---

# Second

Line


More code
---

## Git is case sensitive



```
The name "git" was given by Linus Torvalds when he wrote the very first version. He described the tool as "the stupid content tracker" and the name as (depending on your mood):

random three-letter combination that is pronounceable, and not actually used by any common UNIX command. The fact that it is a mispronunciation of "get" may or may not be relevant.
stupid. contemptible and despicable. simple. Take your pick from the dictionary of slang.
"global information tracker": you're in a good mood, and it actually works for you. Angels sing, and a light suddenly fills the room.
"goddamn idiotic truckload of sh*t": when it breaks
```



GitHub

Milestones

Wiki

Project

Acctions




BG
: Dark  = #222222
: Light = #CCCCCC

P:\__Fritidshus\_Montage\_Specunderlag


echo "# Third" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/Jim20220214/Third.git
git push -u origin main


<!--

> [!IMPORTANT]
> Crucial information necessary for users to succeed.  
> One More line to merge

> [!WARNING]
> Critical content demanding immediate user attention due to potential risks.

-->


<!--STYLE-->
<!--style>

:root {
  --main-bg-color: #333333;
  --main-bg-color: #333333;
}

html, body, ul,li, h1,h2, h3, p, div, table {
    //background-color: #EEEEE;
    color: #DDDDDD;
    background-color: var(--main-bg-color);
    font-family: Menlo, Monaco, monospace;
}
@font-face {
font-family: 'Trade Gothick LT Std';
src:
    local('Trade Gothick LT Std'),
}
@media print {
    html, body, ul,li, h1,h2, h3, p, div, table {
        background-color: orange; 
    }
}
a:active {
    color: green;
}



</style-->
<!--/STYLE-->

---

[Home]: https://jim20220214.github.io/Site/