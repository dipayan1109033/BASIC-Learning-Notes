# Git and GitHub-Basic

**Table of Contents**

- [Git and GitHub-Basic](#git-and-github-basic)
  -	[Introduction](#introduction)
  -	[Using Git](#using-git)
  -	[Basic Git Bash Commands](#basic-git-bash-commands)
  -	[Configure Git](#configure-git)
  -	[Basic Git Commands](#basic-git-commands)
  -	[Cheat Sheet](#cheat-sheet)
  -	[Getting Help](#getting-help)
  -	[Best Practice](#best-practice)
    - [Commit](#commit)
    - [Commit Message](#commit-message)
  -	[Working with Git](#working-with-git)
  -	[Removing Files](#removing-files)
  -	[Ignoring Files](#ignoring-files)
  -	[Git Status and History](#git-status-and-history)
  -	[View the Changes](#view-the-changes)
  -	[Viewing a Commit](#viewing-a-commit)
    - [Viewing details for a specific commit \[2 ways\]](#viewing-details-for-a-specific-commit-2-ways)
    - [To see final version for a specific commit](#to-see-final-version-for-a-specific-commit)
    - [To see all the files for a specific commit](#to-see-all-the-files-for-a-specific-commit)
  -	[Git Restore Files](#git-restore-files)
    - [To restore files from staging area](#to-restore-files-from-staging-area)
    - [Discard the local changes](#discard-the-local-changes)
    - [To remove all untracked files](#to-remove-all-untracked-files)
    - [Restoring a file to an Earlier Version](#restoring-a-file-to-an-earlier-version)
  -	[Git Branch](#git-branch)
  -	[Working with GitHub](#working-with-github)
  -	[Miscellaneous](#miscellaneous)
    - [Check if current directory is a Git repository](#check-if-current-directory-is-a-git-repository)
  -	[References](#references)

  <br>

  ##	Introduction
  -	git is a Version Control System (VCS) for tracking changes in computer files.

  -	It’s a distributed version control system
  -	git is open source and free to download from https://git-scm.com/downloads
  -	GitHub is a code hosting platform for version control and collaboration. 

  ##	Using Git
  -	VS code has source control panel to use essential git features

  -	Also, you can use vscode terminal as a git command window
  -	Most popular extension to get additional git features is GitLens 
  -	Popular git GUI tools are GitKraken and Sourcetree
  -	Using git BASH (emulates Linux environment) is better to use rather cmd for git command line 

  ##	Basic Git Bash Commands
  ```
  mkdir <temp-folder>                      # creating a folder named <temp-folder>
  cd <folder-name>                         # change current directory (changing folder)
  touch <filename.extension>               # to create <filename.extension> file
  echo <first-sentence> > <file-name>      # write <first-sentence> to <file-name>
  echo <second-sentence> >> <file-name>    # append <second-sentence>
  
  code <file-name>		                 # open <file-name> file in vscode
  clear 			                         # clear the git Bash command window
  ```

  ##	Configure Git
  After first time installation, need to specify name, email, default editor, line ending
  These specifications can be one of the three different levels
  1.	**System**: All users
  2.	**Global**: All repositories of the current user
  3.	**Local**: The current repository

  ```
  git config –-global user.name “Dipayan Biswas”
  git config –-global user.email dipayan1109033@gmail.com
  git config –-global core.editor “code –-wait”             # wait for vscode to be closed
  ```

  If you don’t config default editor, “git commit” command will open vim editor to type message for the commit. [In vim editor, **press “i”** for insert mode, then type your commit message. **Press esc** to return from the insert mode and lastly **type “:wq” + enter** to exit from vim editor]

  To open all the configuration settings that are stored in a text file. We can edit that file using our default editor.

  ```
  git config –-global -e
  git config --global --list	      # shows list of configurations already made 
  ```

  Configuring line ending for users from different operating system
  When working with multiple users working different operating system

  ```
  git config –-global core.autocrlf true	      # for windows user
  git config –-global core.autocrlf input	      # for MAC or Linux user
  ```

  ##	Basic Git Commands
  
  ```
  git init                # initialize local git repository
  git add <file(s)>	    # add file(s) to staging area (index)
  git status		        # check status of working tree
  git commit		        # commit changes in index to local repository
  ```
  The followings commands require to link remote repository beforehand  

  ```
  git push		        # push to remote repository
  git pull		        # pull the latest from remote repository
  ```
  It requires when working with multiple peoples

  ```
  git clone		        # clone remote repository into a new local directory
  ```

  #	Cheat Sheet
  Git cheat sheet from Programming with Mosh- Git Tutorial
  https://www.youtube.com/watch?app=desktop&v=8JJ101D3knE

  #	Getting Help

  To get help document for each particular command

  ```
  git config --help
  ```
  If you need short summary of the help for a command

  ```
  git config -h
  ```

  ##	Best Practice
  ### Commit 
  -	Always add changes for a particular task.
  -	Do different commit for different tasks.
  -	We have option to add a portion of a modified file to a commit and rest to another commit
  -	`git add -p <file-name>`
  -	Then it asks for whether we want to stage each particular chuck of code to go into stage area [y/n]

  ### Commit Message
  -	Should describe changes, reasons for change or anything to watch out.
  -	Commit 5 to 10 times a day.

  ##	Working with Git 
  Make a project folder and right click on that folder to open git BASH.
  For first time to add repository, we need to use

  ```
  git init
  ```
  Git uses staging area or the index to review our work before recording a snapshot.
  We add the modified files to the staging area or index, review our changes and if everything is good then we’ll make a commit.

  ```
  git status	                # to see the status of the working directory and the staging area
  git add <file1.txt>	        # add <file1.txt>
  git add *.txt		        # add all .txt files
  git add .			        # add all files

  git commit – m “<commit message>”
  ```
  When you want to add large message to explain some details, use

  ```
  git commit	      # open default editor
  # write comments [with a heading line, give one blank line and then your description] and close the file.
  ```
  ```
  git commit -a -m “<commit message>”	    # do commit skipping the staging area
  git commit -am “<commit message>” 	    # another format but work like above
  ```

  ##	Removing Files
  Remove files from both working directory and staging area

  ```
  git rm <file2.txt>	            # remove <file2.txt>
  git rm *.txt
  ```
  ```
  git rm –-cached <file3.txt>	    # remove file(s) only from staging area
  git rm –-cached -r output/		# remove files only from staging area [here, -r is for recursive removal from the directory]
  ```
  ```
  git mv <main.js> <file3.js>	    # renaming or moving file <main.js> to <file3.js>
  ```

  ##	Ignoring Files

  ```
  git add .gitignore
  ```
  ```
  echo logs-folder/ > .gitignore	    # write “logs-folder/” to .gitignore file
  echo input-images/ >> .gitignore	# append “input-images/” to gitignore file
  code .gitignore		                # open .gitignore file in vscode

  git commit -m “Adding gitignore”
  ```
  This only work if you haven’t already included file(s) or directory(s) in your repository 

  If you already had included in past commit, we need to remove the file(s) from the staging area 

  ```
  git ls-files	                  # shows file in the staging area
  git rm –-cached -r output/		  # remove files only from staging area or index [here, -r is for recursive removal from the directory]
  git commit -m “remove accidently added <folder> from the repository”
  ```

  ##	Git Status and History

  ```
  git status	                   # general use of status
  git status -s 	               # short form of status. 
  On the left gives two info: [??]/[MM]/[AA]/[DD]> [staging-area-status working-directory-status]
  ```
  ```
  git log	# press “space” to go for next log page, press “q” to quit
  git log --oneline		        # shows a short summary of the commit
  git log --online --reverse 	# shows log in reverse order
  ```

  ##	View the Changes
  To review the exact change in the stage area before commit
  
  ```
  git diff –-staged
  ```
  To see the changes that are not staged yet
  
  ```
  git diff
  ```
  To config vscode as out default devtool [2 steps] to view changes

  ```
  git config --global diff.tool vscode	      # just naming our default devtool
  git config --global difftool.vscode.cmd “code --wait --diff $LOCAL $REMOTE”
  ```
  **Note:** vscode needs to be added to path so that it can be run just typing “code” + enter from any directory

  ```
  git config --global -e          # opening .gitconfig in vscode and check if previous command reflects in the .gitconfig file. If not, correct that.
  ```

  Now to see diff through vs code

  ```
  git difftool		            # may ask for permission [y/n]
  git difftool --staged	        # may ask for permission [y/n]
  ```

  ##	Viewing a Commit
  ```
  git log --online    # get unique identifier from history
  ```

  ### Viewing details for a specific commit [2 ways]
  
  ```
  git show [unique-identifier] 	 
  git show HEAD~[n]	        	# n = how many lines down from HEAD
  ```
  ### To see final version for a specific commit
  put [colon] ` : ` after the above show command and specify file to see

  ```
  git show HEAD~2:
  git show HEAD~2:.gitignore	    # if in subdirectory, put full path
  ```
  ### To see all the files for a specific commit

  ```
  git ls-tree HEAD~2	            # display “tree” indicating directory; “blob” indicating file
  ```

  ## Git Restore Files
  
  ### To restore files from staging area

  This restore command take the copy from the next environment. So, in case of the staging area, the next environment is the last commit we have in the repository.

  ```
  git restore --staged <file1.txt>
  git restore --staged *.txt
  git restore --staged .
  ```
  ### Discard the local changes 

  ```
  git restore file1.txt	        # git took a copy from the staging area 
  ```
  ### To remove all untracked files

  ```
  git clean -h
  git clean -fd	                # “f” for force, “d” for remove whole directory
  ```

  ### Restoring a File to an Earlier Version

  ```
  git log --oneline
  git restore --source=HEAD~1 <file1.txt>
  ```

  ##	Git Branch
  Creating branches help to work on different tasks independently and parallel. Also, it keeps the main branch running fine without affecting by the development bugs.

  ```
  git branch <branch-name>	        # create a new branch with <branch-name>
  git checkout <branch-name>          # switch to another branch with name <branch-name>
  git merge <other-branch-name>		# merge <other-branch-name> to the executing branch
  ```


  ##	Working with GitHub
  Create a GitHub repository on https://github.com/ and copy the web URL of the repository having *.git extension.

  ```
  git remote		      # check whether you have already linked to an existing remote repository
  git ls-remote	      # displays references available in a remote repository along with the associated commit IDs.
  ```
  ```
  git remote add origin <remote-repo-url>	# add remote repository with name “origin”
  git push -u origin master	    # push to remote repository “origin”
  ```
  Here, the -u flag adds a tracking reference to the upstream server you are pushing to. It lets you do a git pull without supplying any more arguments. 

  ```
  git pull	            # incorporates changes from a remote repository 
  ```

  ##	Miscellaneous
  ### Check if current directory is a Git repository

  ```
  git rev-parse --is-inside-work-tree
  ```
  1.  prints true if you are in a git repository 
   
  2.   prints false if you are in the .git directory
  3.   gives a fatal error (printing *not a git repository*) if you are not in a git repository.



  ##	References
  [Git & GitHub Crash Course For Beginners](https://www.youtube.com/watch?v=SWYqp7iY_Tc)
  
  [Git Tutorial for Beginners: Learn Git in 1 Hour](https://www.youtube.com/watch?v=8JJ101D3knE)

  Great introduction to use git inside of vscode:<br>
  [How to use Git inside of VSCode - 2020](https://www.youtube.com/watch?v=F2DBSH2VoHQ)
  
  [Official git Documentation](https://git-scm.com/doc)
  

