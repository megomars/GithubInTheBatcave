#Github in the batcave

##Here are 100 things that you need to know about git and github:

### Beginner commands
1. brew install git (install github on a mac with homebrew)
2. git config --global user.name "M H"
3. git config --global user.email "myemail@gmail.com"
4. git config --global color.ui true
5. **git init**
6. **git status** (Which files are staged and which need to be staged?)
7. **git add .** (add all changes to staging)
8. **git commit -m "Message here"** (commit staged changes)
9. git commit -am "message here" (add and commit changes)
10. vim .gitignore (creates a file for ignoring certain files)
  - Icon?
  - .DS_Store
  - !master.txt (do track this)

### Some theory about VCS's
  - distributed (whole project available to everyone)
  - 3 layers
    - working directory (*factory*) (a bare clone does not have a working directory)
    - staging area (index) (*loading dock*) (pick and choose what you want to commit)
    - repository (.git folder)

  - blob (stores the content of the file)
  - git object (40 character hashing algorithm - SHA-1 hash)(compressed with z-lib)
  - tree
  - commit (snapshots)

### Intermediate commands
11. git diff README (difference between working directory content and staged content)
12. git diff --staged README OR git diff --cached README (difference between staged content and committed content)
13. git diff HEAD README (difference between working directory and committed content)
14. git diff 394da3 readme (what changes happened to the readme file since that hash)
15. git diff 434532 4345346 (compare the two hashes)
16. git log (view the history of all your commits) (press j and k to jump up and down)
17. git log --stat (some statistics)
18. git log --oneline (useful for comparing commits)
19. git log --graph (see a graph of the project)
20. git log --pretty --graph --oneline --all --decorate (custom reports) (all branches) [http://git-scm.com/docs/git-log](http://git-scm.com/docs/git-log)
21. gitk (gives you a UI for commits)
22. git branch (which branch are we currently on?)
23. git branch experiment (make a branch called experiment)
24. git checkout experiment (switch to this branch)
25. git checkout -b "bugfix1" (make a new branch and check it out)

26. alias gl='git log --oneline --all --graph --decorate' (here is a cool alias for showing the log)
27. git merge bugfix1 (merge bugfix1 with the master branch)
28. git branch -d bugfix1 (delete branch bugfix1 once you've merged it into master)
29. git rebase experiment2 (keep your history cleaner, rewind all your work to top of master branch)

### Welcome to Github

30. [https://github.com/new](https://github.com/new)
31. git remote add origin git@github.com:nameofrepo/project.git
32. git push -u origin master

### Setup your SSH on github
33. Go to this page and add SSH Key [https://github.com/settings/ssh](https://github.com/settings/ssh)
34. cd ~/.ssh (open all your existing keys)
35. ssh-keygen -t rsa -C "myemail@gmail.com"
36. cat id_rsa.pub
37. (copy the contents of this and paste it into the https://github.com/settings/ssh section)
38. ssh -T git@github.com (check that there is a SSH connection)
