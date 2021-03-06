# Introduction to the Unix shell

## Create and download some test files
- `make example_files`

## The basic anatomy of a command line call

- **`ls`**
- `ls -l`
- `ls -lh`
- `ls test_folder`
- `ls -l test_folder`

## How to get help and documentation

- **`man`**
- `man ls`
- `ls --help`

## Bash keyboard shortcuts

- `TAB` - extend commands and file/folder names
- `Ctrl-c` - Stop the command
- `Ctlr-↑` - Go backward in command history
- `Ctlr-↓` - Go forward in command history
- `Ctrl-a` - Jump to the beginning of a line
- `Ctrl-e` - Jump to the end of a line
- `Ctrl-u` - Remove everything before the cursor position
- `Ctrl-k` - Remove everything after the cursor position
- `Ctrl-l` - Clean the screen
- `Ctrl-r` - Search in command history

## Files, folders, locations

- **`pwd`**
- `ls /`
- `ls unix_course_files`
- `ls /home/toby/unix_course_files`
- `ls ./`
- `ls`
- `ls ../`
- `ls ../../`
- `ls ~/`
- **`cd`**
- `cd unix_course_files`
- `pwd`
- `cd /home/toby/`
- `cd ~/`
- `cd ../`
- `cd`
- `pwd`
- **`mkdir`**
- `mkdir my_first_folder`
- `mkdir my_first_folder`

## Manipulating files and folder

- **`touch`**
- `touch test_file_1.txt`
- `cp test_file_1.txt a_copy_of_test_file.txt`
- `cp test_file_1.txt my_first_folder`
- `cp -r my_first_folder a_copy_of_my_first_folder`
- **`mv`**
- `mv a_copy_of_test_file.txt test_file_with_new_name.txt`
- `mv test_file_with_new_name.txt my_first_folder`
- `touch file1 file2 `
- `mv file1 file2 my_first_folder`
- `touch file1.txt file2.txt file3`
- `ls *txt`
- `mv *txt my_first_folder`
- **`rm`**
- `rm my_first_folder/file1.txt`
- `rm -r my_first_folder`
- **`rmdir`**
- `rmdir my_first_folder`

## File content - part 1

- **`less`**
- `cd unix_course_files`
- `less origin_of_species.txt`
- **`cat`**
- `cat two_lines.txt`
- `cat two_lines.txt three_lines.txt`
- `cat two_lines.txt three_lines.txt > five_lines.txt`
- `cat five_lines.txt`
- **`echo`**
- `echo "Something very creative"`
- **`>`**, **`>>`**
- `echo "Something very creative." > creative.txt`
- `echo "Something very uncreative." > creative.txt`
- `echo "Something very creative." > creative.txt`
- `echo "Something very uncreative." >> creative.txt`
- **`head`** and **`tail`**
- `head origin_of_species.txt`
- `tail origin_of_species.txt`
- **`cut`**
- `cut -c 1-10 origin_of_species.txt`
- `cut -f 1,4 genes.csv`

## File content - part 2

- **`wc`**
- `wc -l origin_of_species.txt`
- **`sort`**
- `sort unsorted_numbers.txt`
- `sort -n unsorted_numbers.txt`
- `sort -rn unsorted_numbers.txt`
- **`uniq`**
- `uniq redundant.txt`
- `uniq -c redundant.txt`
- **`grep`**
- `grep species origin_of_species.txt`
- `grep -i species origin_of_species.txt`
- `grep -ic species origin_of_species.txt`

## Connecting tools

- **`|`**
- `head -n 1000 origin_of_species.txt | grep species | grep wild | tr w m`

## Repeating commands using the `for` loop

# Shell scripting

## Examples analysis

## Retrieving data
- ```
wget ftp://ftp.ncbi.nlm.nih.gov/genomes/archive/old_refseq/Bacteria/\
Salmonella_enterica_serovar_Typhimurium_SL1344_uid86645/\
NC_016810.fna
```

- ```
wget ftp://ftp.ncbi.nlm.nih.gov/genomes/archive/old_refseq/Bacteria/\
Salmonella_enterica_serovar_Typhimurium_SL1344_uid86645/\
NC_016810.gff
```

## Counting the number of features

- `grep -c tRNA NC_016810.gff`
- `cut -f 3 NC_016810.gff | grep -c tRNA`
- `grep -v "#" NC_016810.gff | cut -f 3 | sort | uniq -c`
- `cut -f 3,7 NC_016810.gff | grep gene | sort | uniq -c`
