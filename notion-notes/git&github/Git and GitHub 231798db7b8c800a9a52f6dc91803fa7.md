# Git and GitHub

Favorite: No
Status: Final
Created: July 16, 2025
Edited: July 16, 2025 2:18 AM
Archive: No
Pin: No

To check your git version, you can run the following command:

```jsx
git --version
```

To see the current state of your repository:

```jsx
git status
```

To **config Your settings:**

```jsx
git config --global user.email "[your-email@example.com](mailto:your-email@example.com)"
git config --global [user.name](http://user.name/) "Your Name"
```

Now you can check your config settings:

```jsx
git config --list
```

**Creating a repository(initialising):**

```jsx
git init
```

Usual flow looks like this:

![image.png](Git%20and%20GitHub%20231798db7b8c800a9a52f6dc91803fa7/image.png)

**Complete git flow:**

![image.png](Git%20and%20GitHub%20231798db7b8c800a9a52f6dc91803fa7/image%201.png)

**to stage changes:**

```jsx
git add <file> <file2>
```

OR

```jsx
git add .
```

**Commit changes:**

```jsx
git commit -m "commit message”
```

view **Logs:**

```jsx
git log
```

## **Branches in Git**

![image.png](Git%20and%20GitHub%20231798db7b8c800a9a52f6dc91803fa7/image%202.png)

**HEAD in git:**

The HEAD is a pointer to the current branch that you are working on.

checking all branches in pwd:

```jsx
git branch
```

creating a new branch:

```jsx
git branch bug-fix
```

switching to another branch:

```jsx
git switch bug-fix 
```

OR 

```jsx
git checkout bug-fix
```

creating and switching at same time:

```jsx
git switch -c dark-mode
```

## **Merging branches**

![image.png](Git%20and%20GitHub%20231798db7b8c800a9a52f6dc91803fa7/image%203.png)

```jsx
git merge bug-fix
```

**3 Way merge:**

![image.png](Git%20and%20GitHub%20231798db7b8c800a9a52f6dc91803fa7/image%204.png)

![image.png](Git%20and%20GitHub%20231798db7b8c800a9a52f6dc91803fa7/image%205.png)

**Rename a branch:**

```jsx
git branch -m <old-branch-name> <new-branch-name>
```

Delete a branch:

```jsx
git branch -d <branch-name>
```

## **Diff, Stash and Tags:**

### **Git diff:**

shows the differences between two commits.

```jsx
git diff --staged
```

OR

```jsx
git diff <branch-name-one> <branch-name-two>
```

OR

```jsx
git diff branch-name-one..branch-name-two
```

### **Git Stash:**

Stash is a way to save your changes in a temporary location.

```jsx
git stash
```

**Naming the stash:**

```jsx
git stash save "work in progress on X feature”
```

**View the stash list:**

```jsx
git stash list
```

**Apply the Most Recent Stash:**

```jsx
git stash apply
```

**Apply Specific Stash:**

```jsx
git stash apply stash@{0}
```

**Applying and Drop a Stash:**

```jsx
git stash pop
```

**Drop the stash:**

```jsx
git stash drop
```

**Applying stash to a specific branch:**

```jsx
git stash apply stash@{0} <branch-name>
```

**Clearing the stash:**

```jsx
git stash clear
```

# **Managing History**

## **Rebase in git:**

Git rebase is a powerful Git feature used to change the base of a branch.

> main branch aur hamari branch ka work alag alag ho jaega to bina steps badaye hmm main branch ki chise other branch mai la sakte hai by rebase
> 

```jsx
git checkout feature-branch
git rebase main
```

<aside>
💡

always rebase in other branches and not in the main ones

</aside>

## **Git reflog:**

Git reflog is a command that shows you the history of your commits.

**View the reflog:**

```jsx
git reflog
```

**Find specific commit:**

```jsx
git reflog <commit-hash>
```

### **Recover lost commits or changes:**

```jsx
git reflog <commit-hash>
git reset --hard <commit-hash>
```

# **GitHub**

Setup SSH key using chat-gpt or following steps.

1. **Generate a new SSH key**
    
    To generate a new SSH key, open the terminal and run the following command:
    
    **Terminal window**
    
    `ssh-keygen -t ed25519 -C "your-email@chaicode.com"`
    
    Here ed25519 is the type of key that you are generating. This creates a new SSH key, using the provided email as label.
    
2. **Save the key**
    
    After generating the key, you need to save it to your computer. You can do this by running the following command:
    
    > Enter a file in which to save the key (/Users/YOU/.ssh/id_ALGORITHM): [Press enter]
    > 
    
    At the prompt you can enter passphrase for the key or you can leave it blank. If you leave it blank, the key will be saved without a passphrase.
    
3. **Add key to your ssh-agent**
    
    After saving the key, you need to add it to your ssh-agent. You can do this by running the following command:
    
    Here it is best to refer above link for more information, as Github has a lot of information on this. There is no point in repeating it here.
    
4. **Add key to github**
    
    Use the web ui to add the key to your github account. You can do this by following the instructions on the [Github website](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account?tool=webui).
    

## **Publish Code to Remote Repository:**

Create a new Repo on your system first, add some code and commit it:

```jsx
git init
git add <files>
git commit -m "commit message"
```

You can check the remote url setting by running the following command:

```jsx
git remote -v
```

**Add Remote Repository:**

```jsx
git remote add origin [https://github.com/hiteshchoudhary/chai-something.git](https://github.com/hiteshchoudhary/chai-something.git)
```

**Pushing Code:**

```jsx
git push -u origin main
```

**Fetch code:**

```jsx
git fetch <remote-name>
```

**Pull code:**

```jsx
git pull origin main
```

**Get code from remote repository:**

![image.png](Git%20and%20GitHub%20231798db7b8c800a9a52f6dc91803fa7/image%206.png)