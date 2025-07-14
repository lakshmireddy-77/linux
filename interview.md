---------------------------linux -----------------------
# to check the current user: 
whoami
pwd ---present wrd

# we can filter multiple strings using grep and we can filter single also:
to print single srting : cat <filename> | grep <word>
to print multipe srting : cat <filename> | grep <word>|grep <word>
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
# to view idone number for a file
ls -i <filename>
# to see metadata/all info
stat <filename> 
df -i
# to count the words
wc -w <filename>
# shred command delets the files permenately which is unable to revore
shred --remove <filename>
# to check the architecture info
dmidecode
# to sort the content
cat <filename> | sort
# to check Ip is associated or not
ping <service name>
telnet <service name>
# to see the port number
netstat -lntp
# to check the specfic open port numbers
netstat -putan | grep 22
# to check the size of the floder
du -sh <flodername>
# to see the running logs
pending
# to see the meomory usage
free -h 
# list the top 10 process based on the memory usage
ps aux --sort=%mem | head -n 10

ps --- to display the active process
a ---- show process for all users 
u ----  display the root/user processes
x --- it igones the backgruond processes (demon)

--sort=%mem ---- by deaulat it will give ASC order
# top 10 commands mostly used
cp
mv
cat
less
grep
find
ls
top,htop
systemctl
chmod,chown
df, df -h, df -sh
# restore the lost pem file? if not how can you acess the instances 

---------------------SHELL-------------
# to see the ehich shell are you running
echo $0