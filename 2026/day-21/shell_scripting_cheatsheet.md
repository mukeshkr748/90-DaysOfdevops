## Variables


NAME="Mukesh"
echo $NAME

User Input
read NAME
echo $NAME

If Else
if [ 5 -gt 3 ]
then
 echo "True"
else
 echo "False"
fi

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

Function
greet() {
 echo "Hello"
}

greet

grep
grep "error" file.log

awk
awk '{print $1}' file.txt

sed
sed 's/old/new/g' file.txt


