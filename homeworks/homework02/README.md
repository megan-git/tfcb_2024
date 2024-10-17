# Homework 2: Unix shell

This homework will assess your ability to run commands in the shell and make a simple script.

Replace the lines specified in _italics_ with your answers and save as a text file.


## Problem 0

**60 points**

Complete the interactive tutorial.

_Completed. The instructions for the tutorial were simple._


## Problem 1

**20 points**

**Write a script that outputs some user and location data and moves that output to a newly created directory**

Make a single script that prints out a file called question01.txt. 

This file should contain the following text:

  My username is (your username, but the script needs to work for anyone, not just you)

  My home directory is (your home directory, but the script needs to work for anyone, not just you)

  The contents of the tfcb_2023/lectures/lecture04/ directory are

  (prints the contents of that directory)

This script should also create a directory called homework02, and move question01.txt into the homework02 directory.

An example output answer should be:

My username is campbellm <br>
My home directory is /Users/melody <br>
The contents of the tfcb_2023/lectures/lecture04/ directory are<br>
01-first-steps.md<br>
02-directories<br>
03-redirection<br>
04-vim<br>
05-history<br>
06-scripting<br>
07-more-interactive-shell<br>
README.md<br>
quickref.md<br>
sequence.gb<br>
slides<br>
vader.txt<br>

## Problem 1 Code Below 
_output_file="question01.txt"
new_dir="homework02"
username=$(whoami)
home_dir=$HOME
target_dir="$home_dir/tfcb_2023/lectures/lecture04"
echo 'My username is $username'
  echo 'My home directory is $home_dir'
  echo 'The contents of the tfcb_2023/lectures/lecture04/ directory are <br>
01-first-steps.md<br>
02-directories<br>
03-redirection<br>
04-vim<br>
05-history<br>
06-scripting<br>
07-more-interactive-shell<br>
README.md<br>
quickref.md<br>
sequence.gb<br>
slides<br>
vader.txt<br>'_ 



## Problem 2

**20 points**

**Write a script that uses a loop to output files with specific names**


Make a single script that does the following:

Makes a new directory in homework02 called question02

In that directory, your script should make 25 new files called
file###.txt

the ### should be the numbers from a list you can find here:

tfcb_2023/homeworks/homework02/list.txt

You can make the contents of those files whatever you want (hint: slide 9... )

## Problem 2 Code Below 

_base_dir="$HOME/homework02"
new_dir="$base_dir/question02"
list_file="$HOME/tfcb_2024/homeworks/homework02/list.txt"
mkdir -p "$new_dir"
while IFS= read -r number; do
formatted_number=$(printf "%03d" "$number")
  file_path="$new_dir/file$formatted_number.txt"
  echo "This is file number $formatted_number" > "$file_path"
  
done < "$list_file"

echo "Files have been created in $new_dir."_


