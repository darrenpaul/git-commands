# Helpful Git Commands

### Write all branches to text file
> git branch -l > *\<file-name>.txr*

### Deleting a git branch
> git branch -d \<branch-name>

### Prune Local git branches
> git remote prune origin

# Managing Multiple Git Accounts
### Generate key for personal account
ssh-keygen -t ed25519 -C "personal@email.com" -f ~/.ssh/personal_key

### Generate key for work account
ssh-keygen -t ed25519 -C "work@company.com" -f ~/.ssh/work_key

### Start the ssh-agent
eval "$(ssh-agent -s)"

### Add both keys to ssh-agent
ssh-add ~/.ssh/personal_key
ssh-add ~/.ssh/work_key

### Create or edit ~/.ssh/config:
#### Personal GitHub Account
Host github.com-personal
    HostName github.com
    User git
    IdentityFile ~/.ssh/personal_key

#### Work GitHub Account
Host github.com-work
    HostName github.com
    User git
    IdentityFile ~/.ssh/work_key

## Personal project configuration
cd ~/personal-project
git config user.name "Personal Name"
git config user.email "personal@email.com"

## Work project configuration
cd ~/work-project
git config user.name "Work Name"
git config user.email "work@company.com"


## When Cloning new repos
### Personal repository
git clone git@github.com-personal:username/repo.git

### Work repository
git clone git@github.com-work:company/repo.git
