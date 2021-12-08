# How to use Git and Github

## Git
</br>

### Setup

- Check version of Git: `git --version`

- Configure Git with username and email address: 
    ```
    $git config --global user.name "your-username"
    
    $git config --global user.email "your-email-address"
    ```
</br>

### Repo Manipulation

There are three stages when using git, that is working dir, stage and HEAD. File from working dir needs to be submitted to HEAD via stage.

Notice that HEAD represents the current branch.

- Initialize git repo for current working dir: `git init`
  
- Check git status: `git status`
  
- Add file to stage: `git add filename`
   
   Delete Files: `git rm test.txt`
    
  
- Finalize your updates with a commit: 
     ```
     # commit all files in the current stage; Two methods can be used
    $ git commit -m "msg of commit" -a          # Method 1
    $ git commit -m "msg of commit"             # Method 2

    # commit specific file in the current stage
    $ git commit -m "msg of commit" filename
     ```

- Delete files but not commit yet and want to find it back:
  ```
  # If the file is not submitted to stage
  git checkout -- filename

  # If the file is submitted to stage but not committed
  git reset HEAD filename
  git checkout -- filename
  ```

- Rename files: `git mv file_from file_to`

- See the Git Log: 
    ```
    git log           # Method 1
    git reflog        # Method 2 
                      # (More brief but contain every step including change of branch)
    ```

- Change Version
    ```
     git reflog                      # Check code for different version
     git reset --hard versioncode    # Change version
    ```

- See the difference of between file that has not been submiited to stage and file that has be submitted to stage or finalized(Stage is priority one): `git diff` 
  
</br>

### Branch

- Create a new branch: `git branch name`

- Check current branch: `git status` 

- See list of all branch: `git branch` 

- Switch branch: `git checkout branchname `

- Merge branch: 
  ```
  # Firstly, switch to master branch. Then merge dev branch to master branch.

  git checkout master
  git merge dev(branch name)
  ```

- Delete branch: `git branch -D dev(branch name)`
  
</br>



## Github

- Clone a repo: `git clone https://github.com/ck784101777/MyHome`

- Push: `git push origin `

- Update for creating a new branch: `git push origin newbranch`
  
  Update for deleting a branch: `git push origin :delbranch`


- Update current branch from github

    Notice that this step will not download new files
    ```
    git pull origin github_branch_name
    ```

- Cover current branch using github version

    Notice that in this case, you will lose everything before in this branch. 
  ```
  git fetch --all 
  git reset --hard origin/githubbranch
  ```






