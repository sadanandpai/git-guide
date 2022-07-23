<div align="center">
  <h1>Git Lean Guide</h1>
  Lean but practical guide to every day Git commands
  
  <img width="654" alt="image" src="https://user-images.githubusercontent.com/12962887/170864903-b331fc72-71f6-429b-81d4-b5cceb9d4b9f.png" />
</div>

<br><br>

---

<br>

### 1. I want to clone a project and start going through the code

- Get the repo url/link
- Open your terminal
- Navigate to the location in the terminal where you want your project to be cloned
- Enter the command `git clone url`

<img width="905" alt="image" src="https://user-images.githubusercontent.com/12962887/170861577-d7111658-96df-4b43-918b-2e2ab3395efd.png">
<br>
<br>

---

<br>

### 2. I have cloned the repo. But I am not able to see the proper code!!!

By default the main/master branch is active. Ask which branch has the relevant code

- Navigate inside the cloned folder `cd repo<-name>`
- Enter the command `git checkout <branch-name>`

<img width="654" alt="image" src="https://user-images.githubusercontent.com/12962887/173235836-dfc2039c-d412-4ca6-b4d4-580ef557c8c6.png" />
<br>
<br>

---

<br>

### 3. Someone has made few changes in the code and asked me to pull those changes. What should I do?

- Enter the command `git pull`

<img width="587" alt="image" src="https://user-images.githubusercontent.com/12962887/173235993-7f2ba191-d9bb-4a78-aec3-35f326e46325.png">
<br>
<br>

---

<br>

### 4. I have modified/formatted some code while going through. Now I want the code to be back to the state as it was.

- Enter the command `git reset --hard`

To reset a single file, run the command `git checkout HEAD -- <file-name>`
<br>
<br>

---

<br>

### 5. I have commented and formatted some code for my reference and I want to keep a copy of this with me for personal use.

The changes you have done which you want keep with you only can be created as a separate branch

- Enter the command `git checkout -b <my-personal-branch-name>`
- Stage all the changes using the command `git add *`
- Then save your changes by the command `git commit -m "<some commit message>"`

To go back to the original branch enter the command `git checkout <original-branch-name>`
To see your changes `git checkout <my-personal-branch-name>`

`my-personal-branch-name` is your local branch and not available for anyone else

<img width="555" alt="image" src="https://user-images.githubusercontent.com/12962887/173236172-30ccb855-0b2c-47ae-a711-152f20bc3b67.png">
<br>
<br>

---

<br>

### 6. What if I do not want one of my branch anymore?

You can use the below commands to delete any branch in your local. But be sure that you really want to delete a branch

- Switch to any branch other than your personal branch by entering the command `git checkout main`
- Enter the command `git branch -d <branch-name>`

If it is not allowing to delete the branch, then use the command`git branch -D <branch-name>`

<img width="797" alt="image" src="https://user-images.githubusercontent.com/12962887/173236283-58ff17a0-6d01-424a-9117-0e4d0e13e6fa.png">
<br>
<br>

---

<br>

### 7. I have made some changes to the code on the branch on which all of the developers are working. How can my make my changes published?

To move the changes from your local machine to online (called origin), follow below steps in your terminal

- Add the changed files `git add *`
- Commit the changes `git commit -m "<some commit message>"`
- Push the changes `git push`

<img width="828" alt="image" src="https://user-images.githubusercontent.com/12962887/170865776-dea5f82e-6ae6-4f60-b70a-0fc8d37fd741.png">
<br>
<br>

---

<br>

### 8. What if I want only some of files added and pushed instead of all the changes?

You can add files by mentioning the file/files with relative or fulll path. You can add file one by one or multiple files at a time using the commands

- Add single file `git add <file-name>`
- Add multiple files `git add <file1-name> <file2-name>`

<img width="589" alt="image" src="https://user-images.githubusercontent.com/12962887/170866895-9d9c2f38-dea2-4709-b5ad-dc7764dfa6f5.png">

Similarly, to unstage a file use the command `git reset <file>`
<br>
<br>

---

<br>

### 9. I just committed but forgot to add few files to the commit. Is there a to update the same commit with some modifications?

Yes. You can update the commit by amending your changes.

- To add files `git add <file-name> <file-name> ...`
- To update the commit `git commit --amend --no-edit`

To update with new commit message `git commit --amend -m 'My new commit message'` (This command can also be used to simply update the previous commit message without any code modifications)

`--no-edit` is used to avoid the prompt to edit the commit message. If you want to modify the commit message as well during the update of the commit, then do not include `-m` along with your commit message 

<img width="587" alt="image" src="https://user-images.githubusercontent.com/12962887/180615625-baa2b6f5-2ca5-454a-bfbf-d7115537cdbf.png">

Note: The `amend` updates the previous commit without creating new one on top of previous. (in reality, Git discards the previous commit and replaces it with new commit)
<br>
<br>

---

<br>

### 10. I created a commit and also pushed it. Is it possible to update that commit now?

Yes. You can update the commit even after it is pushed. Everything will follow as mentioned in the previous question, but you will have to force push.

- `git add <file-name> <file-name> ...`
- `git commit --amend --no-edit` or `git commit --amend`
- `git push -f` or `git push --force`

You need to be very careful while pushing forcefully, as it may eliminate other commits if someone has done in between. Make sure you are working on the branch and no one else is similutaneous working on the same or branching out from the branch at your commit.
<br>
<br>

---

<br>

### 11. I have made some changes in a branch. But it is partially completely. How can I continue from the same point in future?

If you are making some changes and need to move on to some other work and then come back, in such case either you can commit or store (stash) the changes.

- `git stash save '<name of the change>` -u

To retrieve the changes once you are back,

- `git stash apply <n>`

where n is the stash number. To get the list of stashes `git stash list`

<img width="819" alt="image" src="https://user-images.githubusercontent.com/12962887/180613172-aa7aca8e-a269-4af4-94dc-9a8055962b91.png">
<br>
<br>

---

<br>

### 12. After applying the stash, I am getting a lot of conflicts in the code.

If there are changes in the code on the region of the stashed code, it is expected to get the conflicts. You will have manually resolve and the conflicts carefully.

<img width="596" alt="image" src="https://user-images.githubusercontent.com/12962887/180613095-a8e08426-1d15-4a31-956b-55bfdfbdb84d.png">

Below is the view of the VSCode, which helps in easily resolving the conflicts.
![image](https://user-images.githubusercontent.com/12962887/180612978-fffd4307-0045-4fd3-b52c-394d1d9a0059.png)
<br>
<br>

---

<br>

### 13. I have committed my changes. How can I undo my change?

You can undo the commit resetting the HEAD. If you just want to undo the commit but let the changes be present then use `soft` attribute else if you do want the commit along with the changes then use `hard` attribute

- `git reset --soft HEAD~1` (undo with changes preserved)

- `git reset --hard HEAD~1` (undo with changes removed)
  <br>
  <br>

---

<br>

### 14. When I am trying to push my changes, getting a rejected message. I am stuck!!!

The rejection could be because the remote branch might be ahead of the local branch. Different techniques can be used here to achieve sync
Undo your commit first. Then pull the remote changes & push your changes

- Undo your commit by running `git reset --soft HEAD~1` (1 represents undoing 1 commit)
- `git pull`
- `git commit -m "<some commit message>"` (commit your changes again)
- `git push`

![image](https://user-images.githubusercontent.com/12962887/173234060-43c76e48-14cb-4680-bdcd-aaa9cd0e64d4.png)
<br>
<br>

---

<br>

### 15. I have followed the above procedure. But when I pulled the changes, it is showing the conflicts. How can I proceed?
