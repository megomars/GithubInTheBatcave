# Github in the batcave

## Here are 100 things that you need to know about git and github:

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
  - Icon (then press ctrl + v, enter, ctrl + v, enter, [Should look like this Icon^M^M])
  - Add to your gitignore global config file in ~/.gitignore_global.



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
11. git diff README.md (difference between working directory content and staged content)
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
26. git branch --all (all local and remote branches)
27. alias gl='git log --oneline --all --graph --decorate' (here is a cool alias for showing the log)
28. git merge bugfix1 (merge bugfix1 with the master branch)
29. git branch -d bugfix1 (delete branch bugfix1 once you've merged it into master)
30. git rebase experiment2 (keep your history cleaner, rewind all your work to top of master branch)

  ### Welcome to Github

31. [https://github.com/new](https://github.com/new)
32. git remote add origin git@github.com:nameofrepo/project.git (git remote -v shows you the path of the remote branch)
33. git push -u origin master

  ### Setup your SSH on github
34. Go to this page and add SSH Key [https://github.com/settings/ssh](https://github.com/settings/ssh)
35. cd ~/.ssh (open all your existing keys)
36. ssh-keygen -t rsa -C "myemail@gmail.com"
37. cat id_rsa.pub
38. (copy the contents of this and paste it into the https://github.com/settings/ssh section)
39. ssh -T git@github.com (check that there is a SSH connection)
40. git branch -a (look at all your master branches)
41. (merge pull request)
42. git pull (get all the files from github - same as performing git fetch and then git merge)
43. git clone https://github.com/jashkenas/coffee-script.git
44. git fetch (pull changes first from github and then merge if you want to, you can then git diff master origin/master to compare the changes and then git merge origin/master)

  ### Github pages
45. Github pages allows you to host a static page

  ### Advanced commands
46. git add -i (interactive add, you can add a part of a file)
47. git stash (stash changes to the side for now)
48. git stash list (shows you all the stashed parts of the project)
49. git stash save "I'm just keeping this on the side for now - like a temporary commit"
50. git stash apply (pull the last stash back in the folder)
41. git stash drop stash@{0} (delete that stash)
52. git stash pop (pull the stash back in the folder and delete it)
53. git push origin experiment (push your experiment branch to github)
54. git diff --name-only master experiment (differences between master and experiment branches)
55. git push origin --delete experiment (deletes a remote branch)

  ### Reverting to older versions
56. git checkout nameoffile.txt (brings back the deleted file)
57. git reset HEAD nameoffile.txt (unstage a file that was staged)
58. git reset --hard HEAD (reset to last commit)
59. **git revert 35454356567e4df656344**
    - first get the git log and copy the SHA-1 Hash

  ### Releasing your software
60. git tag -a RELEASE001 (annotated tag, add a description in the editor)
61. git show (show contents of your tags)
62. git show RELEASE001 (show contents of your tags)
63. git push --tags (pushes tags to github)
64. git checkout RELEASE001 (go back to that release)

  ### Github workflow best practices
65. File an issue with the project
66. Forking a repo (fork the repo, then git clone then create a branch)
67. Create a LICENSE
68. Recommend changes to original project (new pull request)
70. Accept pull requests (merge pull request, similar to a code review)
71. Draft a new release (menu in the tags page. Should use github flavored markdown)
72. gists (small code snippets) (link, embed or clone gists)
73. git describe --tags (what releases are available)
74. [http://try.github.io](http://try.github.io) (interactive tutorial)
75. [http://help.github.com](http://help.github.com)

  ### Working in teams on Github
81.
82.
83.
84.

  ### Issues
85. Closed issues, open issues, search and labels
86. Milestones
87. New Issue - add in color labels
88. Related to \#1 (will link the issue to the first issue)
89. fixed \#2 (in the comments will automatically close the issue)


  ### Graphs and Network
90. Contributors, commits, Code frequency, punchcard

  ### Trello
91. Service hooks

  ### Continuous integration
92. Travis CI or Jenkins
93. Travis bot (read access)

  ### Hubot
