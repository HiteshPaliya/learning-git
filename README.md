# README

### This is the repo I was testing upon while learning how to use the git cli tool.  

#### Configuring User Settings  
```
git config --global user.name "My Name"
git config --global user.email my_email@domain.com  
```

#### Setting default Editor - VSCode  
```
git config --global core.editor "code --wait"
```

#### Opening golbal configuration settings in default editor  
```
git config --global -e
```

#### Handling end of lines  
```
#Windows -> \r\n (Carriage Return + Line Feed)
#Linux/Mac -> \n (Line Feed)

git config --global core.autocrlf input  
#Set 'true' instead of 'input' on windows system  
```

#### Initialising a repository
```
mkdir project
cd project
git init 
``` 

#### Staging files
```
echo hello > file1.txt
echo hello > file2.txt
git add file1.txt file2.txt  OR  git add *.txt  OR  git add .
git status
```

#### Commiting snapshots to save files in the repo
```
git commit -m "Initial Commit"
```

#### Skipping the staging area
```
echo test >> file1.txt
git commit -am "Fix the bug"
```

#### View files in staging area
```
git ls-files
```

#### Removing file
```
rm file2.txt
git status
git ls-files
git add files2.txt
git commit -m "Remove unused code"
```

#### Removing/moving files
```
mv file1.txt main.js
git status
git add file1.txt main.js
git status  
  
#All that in one command
git mv main.js file1.txt
git commit -m "Refactor code"
```

#### Ignoring files (Won't work for files and folders already residing in the repo)
```
mkdir logs
echo testing logs/dev.log
echo logs/ > .gitignore
git add .gitignore
git commit -m "Add gitignore"
```

#### Removing files from staging area so that previous files can be added in .gitignore
```
git ls-files
git rm -h
git rm --cached -r <file> #Remove files recursively from staging (index) area
git ls-files
git commit -m "Remove file that was accidently commited"

#Now you can add files/folders in .gitignore and it won't be uploaded from now on!
* Learn more what to add in .gitignore: https://github.com/github/gitignore
```

#### Viewing history
```
git log
git log --oneline
git log --oneline --reverse
```

#### Viewing Commit
```
git show 921a2  #using identifier from `git log --oneline` 
(identifier's first few characters will work if it is unique)

git show HEAD~1 #Backtrack from HEAD pointer to specified number backwards

git show HEAD~1:bin/app.bin
#View content of the files in the previous commit
git show HEAD~1:.gitignore
```

#### View all the files of the previous commits (Files = blobs, Directories = tree)
```
git ls-tree HEAD~1
```

#### Unstaging files
```
git restore --staged file1.js
OR
git restore --staged .
```
