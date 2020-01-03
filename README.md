## Welcome to Scripts!

This repo is a collection of scripts.

### Python3 packages

This is used to remove all the packages installed on root directory / the machine rather than installing it in virtualenv.

    pip3 freeze --local | xargs pip3 uninstall -y
 
### Cut command
 
 Suppose there is a file data.csv and you want to take out characters 1 to 5 
 
    cat data.csv | cut -c 1-5
    -c means column
 
 
 
 Suppose the data.csvfile contains data like 1 
 >System ID,School,Phone,Address,City,State,Zip,Type,Principal
 >569,Happy Valley Elementary School,814-555-1212,332 Innovation Boulevard,State College,PA,16801,Elementary,Mr. Jenkins

 The command for taking out values of the first col by using the delimiter ','
 
 > cut data.csv | cut -d ',' -f 1
 >
 >  -d is delimiter and -f is field number
 
 
### Cat command 

 Suppose there is a file and we need to read contents of a file 
 
    cat file.txt
    cat file1.txt file2.txt
    This is used to show  multiple files 


 Copy contents of file1 to file2
 
    cat file1.txt > file2.txt
 
 Appemnd contents of file1 to file2
 
    cat file1.txt >> file2.txt
 
 ### SHEBANG CONSTRUCT 
 
    #!/bin/sh
    This is used to tell the system that this is a shell script
 
 ### Grep command 
 
 Match all words starting with Ind
 
    cat words.txt | grep "Ind.*"

Match all words ending with age

    cat words.txt | grep ".*age$"
 
Grep file filename

    grep -HRi 'json' *
    -R  is recursive, -H is filename, -i is case-insensitive

 
 ### tty
 
    Fucntion: Print file name of standard input's terminal
 
 ### Piping 
 
 > A pipe is a form of redirection that is used in Linux and other Unix-like operating systems to send the output of one program to another program for further processing
 
 
 ### Sort 
 
 > cat words.txt | sort -k 2 
 > -k select the field upon which the sorting to be implemented 
 
 ### Uniq
 
 Filter out repeated lines 
 
 > cat nums.txt | uniq
 
    Input 
    
    1
    2
    2
    3
    3
    3
 
 >   Applying command to above input 
 >   cat input.txt | uniq -c
 >  -c represents count of each element mae unique
 
    Output 
    
    1 1
    2 2 
    3 3  
   
   ### Head, tail and tr
   
   Get lines from 345 to 360
   
   > cat words.txt | head -360 | tail -15
   
   Replace the charaters 
   
   > cat data.csv | tr '[a-z][A-Z]' '[A-Z][a-z]'
   > Replaces the [a-z][A-Z] by [A-Z][a-z] repectively
 
   Replacing numbers with x 
   
   > cat data.csv | tr '[0-9]' 'x'
   
   Remove all the digits 
   
   > cat data.csv | tr -d '[0-9]'
   > . -d represents delete flag
   
   
### Regex in bash 

Match all words starting with non-vowel and end with a vowel

  >  cat filename | grep "^[^aeiou].*[aeiou]" 
  
  
 Regex important concepts :
 
    '.' (dot) - Matches any single character except the newline character (\n).
    '*' (star) - Matches zero or more occurrence of the immediately preceding character.
    '<' - Matches the beginning of a word
    '>' - Matches the ending of a word
    '^' - Matches the beginning of a line
    '$' - Matches the end of a line  
    '{m}' - Matches the exactly regex ‘m’
    '{m,}' - Matches the at least regex ‘m’
    '{m,n}' - Matches the preceding regex ‘m’ to ‘n’ times
    
    '[:alnum:]' - Alphanumeric characters; same as [a-zA-Z0-9]
    '[:digit:]' - Digits; same as [0-9]
    '[:punct:]' - Punctuation characters

### Sed - Stream Editor

     Sed is a powerful text stream editor which can do insertion, deletion, search and replace.
     
   #### Examples
   
   
     Input:  
     cat
     caat
     caaat
     caaaat
     caaaaat

     sed 's/a\{2,\}/a/g' input
     s is substitution
     2nd parameter is string to be replaced
     3rd parameter is by whom string is to be replaced
     4th parameter decides the occurences. 
     Here, g represents global or all occurences. It can be replaced by 1,2,etc. 3g means from 3rd occurence to last. 
   
   
     sed '3 s/a\{2,\}/a/g' input
     Here ONLY 3rd line gets modified
   
   
     sed 's/a\{2,\}/a/p' input
     prints only modified lines 
  
   
   ### Git 
   
   Git Squash
   
     git rebase -i HEAD~2
     
     pick 2d603a2 chore: practicing git .   - oldest commit 
     pick 5e4eae4 Squash test .   - latest commit

     pick 2d603a2 chore: practicing git .   - oldest commit 
     sqash 5e4eae4 Squash test .   - latest commit
     
     Change last N-1 commits to squash 
     
     This is used to squash last N commits into 1 commit 
  
 ### Remove all pycache files
 
    find . | grep -E "(__pycache__|\.pyc|\.pyo$)" | xargs rm -rf
    
 ### Revert remote branch to previous commit 
 
     git reset --hard <commit-hash>
     git push -f origin master
