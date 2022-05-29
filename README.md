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

<img width="567" alt="image" src="https://user-images.githubusercontent.com/12962887/170878556-4a48dd7c-96f6-43e7-b317-32c78ad24fcd.png">

#### 3. Someone has made few changes in the code and asked me to pull those changes. What should I do?

- Enter the command `git pull`

<img width="654" alt="image" src="https://user-images.githubusercontent.com/12962887/170861829-b9e2adbf-b960-4322-a7b5-6410ba354e13.png">

#### 4. I have modified/formatted some code while going through. Now I want the code to be back to the state as it was.

- Enter the command `git reset --hard`

#### 5. I have commented and formatted some code for my reference and I want to keep a copy of this with me for personal use.

The changes you have done which you want keep with you only can be created as a separate branch

- Enter the command `git checkout -b <my-personal-branch-name>`
- Stage all the changes using the command `git add *`
- Then save your changes by the command `git commit -m "<some commit message>"`

To go back to the original branch enter the command `git checkout -b <original-branch-name>`
To see your changes `git checkout -b <my-personal-branch-name>`

`my-personal-branch-name` is your local branch and not available for anyone else

<img width="610" alt="image" src="https://user-images.githubusercontent.com/12962887/170863218-681fc59d-5d2d-4021-8028-2a7b5d7d34aa.png">

#### 6. What if I do not want one of my branch anymore?

You can use the below commands to delete any branch in your local. But be sure that you really want to delete a branch

- Switch to any branch other than your personal branch by entering the command `git checkout main`
- Enter the command `git branch -d <branch-name>`

If it is not allowing to delete the branch, then use the command`git branch -D <branch-name>`

<img width="610" alt="image" src="https://user-images.githubusercontent.com/12962887/170863291-edb848bf-5994-431a-b367-44e40a8ddf61.png">

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

#### 9. When I am trying to push my changes, but getting a rejected message. I am stuck!!!

The rejection could be because the remote branch might be ahead of the local branch. Pull the changes from remote and then proceed

- TODO
