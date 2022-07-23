<div align="center">
  <h1>Git Lean Guide</h1>
  Lean but practical guide to every day Git commands
  
  <img width="654" alt="image" src="https://user-images.githubusercontent.com/12962887/170864903-b331fc72-71f6-429b-81d4-b5cceb9d4b9f.png" />
</div>

#### 1. I want to clone a project and start going through the code

- Get the repo url/link
- Open your terminal
- Navigate to the location in the terminal where you want your project to be cloned
- Enter the command `git clone url`

<img width="905" alt="image" src="https://user-images.githubusercontent.com/12962887/170861577-d7111658-96df-4b43-918b-2e2ab3395efd.png">

#### 2. I have cloned the repo. But I am not able to see the proper code!!!

By default the main/master branch is active. Ask which branch has the relevant code

- Navigate inside the cloned folder `cd repo<-name>`
- Enter the command `git checkout <branch-name>`

<img width="654" alt="image" src="https://user-images.githubusercontent.com/12962887/173235836-dfc2039c-d412-4ca6-b4d4-580ef557c8c6.png" />

#### 3. Someone has made few changes in the code and asked me to pull those changes. What should I do?

- Enter the command `git pull`

<img width="587" alt="image" src="https://user-images.githubusercontent.com/12962887/173235993-7f2ba191-d9bb-4a78-aec3-35f326e46325.png">

#### 4. I have modified/formatted some code while going through. Now I want the code to be back to the state as it was.

- Enter the command `git reset --hard`

To reset a single file, run the command `git checkout HEAD -- <file-name>`

#### 5. I have commented and formatted some code for my reference and I want to keep a copy of this with me for personal use.

The changes you have done which you want keep with you only can be created as a separate branch

- Enter the command `git checkout -b <my-personal-branch-name>`
- Stage all the changes using the command `git add *`
- Then save your changes by the command `git commit -m "<some commit message>"`

To go back to the original branch enter the command `git checkout -b <original-branch-name>`
To see your changes `git checkout -b <my-personal-branch-name>`

`my-personal-branch-name` is your local branch and not available for anyone else

<img width="555" alt="image" src="https://user-images.githubusercontent.com/12962887/173236172-30ccb855-0b2c-47ae-a711-152f20bc3b67.png">

#### 6. What if I do not want one of my branch anymore?

You can use the below commands to delete any branch in your local. But be sure that you really want to delete a branch

- Switch to any branch other than your personal branch by entering the command `git checkout main`
- Enter the command `git branch -d <branch-name>`

If it is not allowing to delete the branch, then use the command`git branch -D <branch-name>`

<img width="797" alt="image" src="https://user-images.githubusercontent.com/12962887/173236283-58ff17a0-6d01-424a-9117-0e4d0e13e6fa.png">

#### 7. I have made some changes to the code on the branch on which all of the developers are working. How can my make my changes published?

To move the changes from your local machine to online (called origin), follow below steps in your terminal

- `git add *`
- `git commit -m "<some commit message>"`
- `git push`

<img width="828" alt="image" src="https://user-images.githubusercontent.com/12962887/170865776-dea5f82e-6ae6-4f60-b70a-0fc8d37fd741.png">

#### 8. What if I want only some of files added and pushed instead of all the changes?

You can add files by mentioning the file/files with relative or fulll path. You can add file one by one or multiple files at a time using the commands

- `git add <file-name>`
- `git add <file1-name> <file2-name>`

<img width="589" alt="image" src="https://user-images.githubusercontent.com/12962887/170866895-9d9c2f38-dea2-4709-b5ad-dc7764dfa6f5.png">

Similarly, to unstage a file use the command `git reset <file>`

#### 9. I have made some changes in a branch. But it is partially completely. How can I continue from the same point in future?

If you are making some changes and need to move on to some other work and then come back, in such case either you can commit or store (stash) the changes.

- `git stash save '<name of the change>`

To retrieve the changes once you are back,

- `git stash apply <n>`

where n is the stash number. To get the list of stashes `git stash list`

<img width="818" alt="image" src="https://user-images.githubusercontent.com/12962887/180604593-4849465d-80ff-4ed0-b2a2-9b400932100e.png">

#### 10. I have committed my changes. How can I undo my change?

You can undo the commit resetting the HEAD. If you just want to undo the commit but let the changes be present then use `soft` attribute else if you do want the commit along with the changes then use `hard` attribute

- `git reset --soft HEAD~1` (undo with changes preserved)

- `git reset --hard HEAD~1` (undo with changes removed)

#### 11. When I am trying to push my changes, getting a rejected message. I am stuck!!!

The rejection could be because the remote branch might be ahead of the local branch. Different techniques can be used here to achieve sync
Undo your commit first. Then pull the remote changes & push your changes

- Undo your commit by running `git reset --soft HEAD~1` (1 represents undoing 1 commit)
- `git pull`
- `git commit -m "<some commit message>"` (commit your changes again)
- `git push`

![image](https://user-images.githubusercontent.com/12962887/173234060-43c76e48-14cb-4680-bdcd-aaa9cd0e64d4.png)

#### 10. I have followed the above procedure. But when I pulled the changes, it is showing the conflicts. How can I proceed?
