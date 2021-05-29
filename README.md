# README

### This is the repo I was testing upon while learning how to use the git cli tool.  

#### Configuring git    
# User Settings  
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
