Day 21 – Shell Scripting Cheat Sheet

Shebang

#!/bin/bash

Variables

NAME="Mukesh"
echo $NAME

User Input

read NAME
echo $NAME

Command Line Arguments

echo $1
echo $2
echo $#
echo $@

If-Else Statement

if [ 5 -gt 3 ]
then
    echo "True"
else
    echo "False"
fi

Case Statement


read choice

case $choice in
    start) echo "Starting..." ;;
    stop) echo "Stopping..." ;;
    *) echo "Invalid Option" ;;
esac

For Loop


for i in 1 2 3
do
    echo $i
done

While Loop

count=1

while [ $count -le 3 ]
do
    echo $count
    ((count++))
done


Functions

greet() {
    echo "Hello Mukesh"
}

greet

File Checks


if [ -f file.txt ]
then
    echo "File Exists"
fi

if [ -d myfolder ]
then
    echo "Directory Exists"
fi


Exit Status

ls
echo $?

grep

grep "error" file.log

awk

awk '{print $1}' file.txt

sed

sed 's/old/new/g' file.txt

sort

sort file.txt

uniq

uniq file.txt

cut

cut -d "," -f1 data.csv


Error Handling

set -e
set -u
set -o pipefail


Debugging

set -x

Make Script Executable

chmod +x script.sh
./script.sh

Useful Commands

pwd
ls -la
df -h
free -m
top
ps aux

Cron Job Example

crontab -e

0 2 * * * /home/user/backup.sh

Backup Command

tar -czvf backup.tar.gz myfolder/

Log Analysis

grep "ERROR" app.log
grep -c "ERROR" app.log


