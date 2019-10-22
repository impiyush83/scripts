## Welcome to Scripts!

This repo is a collection of scripts.

### Python3 packages

This is used to remove all the packages installed on root directory / the machine rather than installing it in virtualenv.

 >  pip3 freeze --local | xargs pip3 uninstall -y
 
### Cut command
 
 Suppose there is a file data.csv and you want to take out characters 1 to 5 
 
 > cat data.csv | cut -c 1-5
 >
 > -c means column
 
 
 
 Suppose the data.csvfile contains data like 1 
 >System ID,School,Phone,Address,City,State,Zip,Type,Principal
 >569,Happy Valley Elementary School,814-555-1212,332 Innovation Boulevard,State College,PA,16801,Elementary,Mr. Jenkins

 The command for taking out values of the first col by using the delimiter ','
 
 > cut data.csv | cut -d ',' -f 1
 >
 >  -d is delimiter and -f is field number
 
 
### Cat command 

 Suppose there is a file and we need to read contents of a file 
 
 > cat file.txt
 > cat file1.txt file2.txt
 > This is used to show  multiple files 


 Copy contents of file1 to file2
 
 > cat file1.txt > file2.txt
 
 Appemnd contents of file1 to file2
 
 > cat file1.txt >> file2.txt
 
 ### SHEBANG CONSTRUCT 
 
 > #!/bin/sh
 > This is used to tell the system that this is a shell script
 
 ### Grep command 
 
 Match all words starting with Ind
 
 > cat words.txt | grep "Ind.*"

Match all words ending with age

 > cat words.txt | grep ".*age$"
 
Grep file filename

 > grep -HRi 'json' *
 > -R  is recursive, -H is filename, -i is case-insensitive

 
 ### tty
 
 > Fucntion: Print file name of standard input's terminal
 
