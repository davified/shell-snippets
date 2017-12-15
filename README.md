# Python

### Creating a python3 conda env

conda create -n venv python=3
source activate venv
conda install ipykernel
python -m ipykernel install --name my_venv

### Removing a conda env
conda remove --name my_venv --all

### Creating a env 
conda create -n python36 python=3.6 anaconda

### See all conda envs
conda env list

### Activating and deactivating conda virtual envs
source activate my_venv
source deactivate 

# Git

## Purge a particular file from git history 
git filter-branch --force --index-filter \\n'git rm --cached --ignore-unmatch path/to/file/to/be/purged' \\n--prune-empty --tag-name-filter cat -- --all
git gc

To check if a file is in git log or not, run the following before and after purging:
git log --stat | grep 'my_filename'

After rewriting the git history, collaborators on the repo will need to run the following:
1) git fetch
2) git reset --hard origin/master 

### To see git diff inline and with color:
git diff --word-diff=color

### To see list of files that have changed in a given commit
git diff-tree --no-commit-id --name-only -r <commit-sha>

# Useful Mac terminal commands

### Find processes running on a port and kill process
lsof -i:8080 # To list any process listening to the port 8080
kill $(lsof -t -i:8080) #To kill any process listening to the port 8080

# Linux
### List all users on a VM:
cut -d: -f1 /etc/passwd

### scp file from local to remote host
scp /path/to/local/file  <username>@<host-ip>:/path/to/store/file
scp -r /path/to/local/directory  <username>@<host-ip>:/path/to/store/directory


# Kaggle
kg download -u <your username> -p <your password> -c <name-of-competition>
