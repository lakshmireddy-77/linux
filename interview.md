# to check the current user: 
whoami
pwd ---present wrd

# we can filter multiple strings using grep and we can filter single also:
to print single srting : cat <filename> | grep <word>
to print multipe srting : cat <filename> | grep <word> | grep <word>
it will give result 2 words combination
# we can filter multiple strings using egrep
to print multipe srting : cat <filename> | grep '(<word>| <word>)
it will give either 2 words combination/both combination

# to read the file without using CAT command 
vi,less,nano

# to check the file permissions :
stat <filename>
# to check the file type :
file <filename>
# to check the file size :
du -h <filename>
# to check the IP :
hostname -I

# to search file in the location:
find /path -name <filename>
# to search file type:
find /path -type f ---> It will give all files
find /path -type d ---> It will give all floders
# to search file larger than 100mb:
find /path -size +10M