Vazifa 10.15.0.73 ushbu ip manzil bizga berilgan edi ssh uchun .
─(onyx㉿kali)-[~]
└─$ ssh alex@10.15.0.73
alex@10.15.0.73's password:
Welcome to Ubuntu 26.04 LTS (GNU/Linux 6.17.2-1-pve x86_64)
- Documentation: https://docs.ubuntu.com
- Management: https://landscape.canonical.com
- Support: https://ubuntu.com/pro
Last login: Wed Jun 24 20:42:10 2026 from 10.15.1.19
- alex@haad-b6602224:~$ls -la
total 32
drwxr-x--- 3 alex alex 4096 Jun 24 20:45 .
drwxr-xr-x 4 root root 4096 Jun 24 20:38 ..
-rw------- 1 alex alex   55 Jun 24 20:45 .bash_history
-rw-r--r-- 1 alex alex  220 Feb 13 12:16 .bash_logout
-rw-r--r-- 1 alex alex 3771 Feb 13 12:16 .bashrc
drwx------ 2 alex alex 4096 Jun 24 20:42 .cache
-rw-r--r-- 1 alex alex  807 Feb 13 12:16 .profile
-rw------- 1 alex alex  240 Jun 24 20:38 user.txt
alex@haad-b6602224:~$ etc/paaswd
-bash: etc/paaswd: No such file or directory
alex@haad-b6602224:~$cat /etc/passwd
root:x:0:0:root:/root:/bin/bash
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin
sys:x:3:3:sys:/dev:/usr/sbin/nologin
sync:x:4:65534:sync:/bin:/bin/sync
games:x:5:60:games:/usr/games:/usr/sbin/nologin
man:x:6:12:man:/var/cache/man:/usr/sbin/nologin
lp:x:7:7:lp:/var/spool/lpd:/usr/sbin/nologin
mail:x:8:8:mail:/var/mail:/usr/sbin/nologin
news:x:9:9:news:/var/spool/news:/usr/sbin/nologin
uucp:x:10:10:uucp:/var/spool/uucp:/usr/sbin/nologin
proxy:x:13:13:proxy:/bin:/usr/sbin/nologin
www-data:x:33:33:www-data:/var/www:/usr/sbin/nologin
backup:x:34:34:backup:/var/backups:/usr/sbin/nologin
list:x:38:38:Mailing List Manager:/var/list:/usr/sbin/nologin
irc:x:39:39:ircd:/run/ircd:/usr/sbin/nologin
_apt:x:42:65534::/nonexistent:/usr/sbin/nologin
nobody:x:65534:65534:nobody:/nonexistent:/usr/sbin/nologin
systemd-network:x:998:998:systemd Network Management:/:/usr/sbin/nologin
dhcpcd:x:997:997:DHCP Client Daemon:/usr/lib/dhcpcd:/bin/false
messagebus:x:996:996:System Message Bus:/nonexistent:/usr/sbin/nologin
syslog:x:100:101::/nonexistent:/usr/sbin/nologin
systemd-resolve:x:990:990:systemd Resolver:/:/usr/sbin/nologin
_chrony:x:989:989:Chrony Daemon:/var/lib/chrony:/usr/sbin/nologin
sshd:x:988:65534:sshd user:/run/sshd:/usr/sbin/nologin
postfix:x:101:103:Postfix MTA:/var/spool/postfix:/usr/sbin/nologin
uuidd:x:102:105::/run/uuidd:/usr/sbin/nologin
tcpdump:x:986:986:tcpdump:/nonexistent:/usr/sbin/nologin
ftp:x:103:108:ftp daemon:/srv/ftp:/usr/sbin/nologin
nodir:x:1000:1000::/home/nodir:/bin/bash
alex:x:1001:1001::/home/alex:/bin/bash
alex@haad-b6602224:~$
- cd /home/alex:/bin/bash
-bash: cd: /home/alex:/bin/bash: No such file or directory
- alex@haad-b6602224:~$/home/alex:/bin/bash
-bash: /home/alex:/bin/bash: No such file or directory
alex@haad-b6602224:~$
- cd /home/alex
- alex@haad-b6602224:~$ls -la
total 32
drwxr-x--- 3 alex alex 4096 Jun 24 20:45 .
drwxr-xr-x 4 root root 4096 Jun 24 20:38 ..
-rw------- 1 alex alex   55 Jun 24 20:45 .bash_history
-rw-r--r-- 1 alex alex  220 Feb 13 12:16 .bash_logout
-rw-r--r-- 1 alex alex 3771 Feb 13 12:16 .bashrc
drwx------ 2 alex alex 4096 Jun 24 20:42 .cache
-rw-r--r-- 1 alex alex  807 Feb 13 12:16 .profile
-rw------- 1 alex alex  240 Jun 24 20:38 user.txt
alex@haad-b6602224:~$
- cat user.txt
FLAG{alex_has_entered_the_system_98234710}

2 qismda men root ni home papkasiga o’tishim kerak edi, root ni home papkasidagi flag ni olish uchun. 

alex@haad-b6602224:~$ su root
Password:

root@haad-b6602224:/home/alex# ls -la
total 36
drwxr-x--- 3 alex alex 4096 Jun 25 16:29 .
drwxr-xr-x 4 root root 4096 Jun 24 20:38 ..
-rw------- 1 alex alex   55 Jun 24 20:45 .bash_history
-rw-r--r-- 1 alex alex  220 Feb 13 12:16 .bash_logout
-rw-r--r-- 1 alex alex 3771 Feb 13 12:16 .bashrc
drwx------ 2 alex alex 4096 Jun 24 20:42 .cache
-rw-r--r-- 1 alex alex  807 Feb 13 12:16 .profile
-rwxrwxr-x 1 alex alex    8 Jun 25 16:29 sh
-rw------- 1 alex alex  240 Jun 24 20:38 user.txt

root@haad-b6602224:/home/alex# /etc/passwd
bash: /etc/passwd: Permission denied

root@haad-b6602224:/home/alex# ls -la
total 36
drwxr-x--- 3 alex alex 4096 Jun 25 16:29 .
drwxr-xr-x 4 root root 4096 Jun 24 20:38 ..
-rw------- 1 alex alex   55 Jun 24 20:45 .bash_history
-rw-r--r-- 1 alex alex  220 Feb 13 12:16 .bash_logout
-rw-r--r-- 1 alex alex 3771 Feb 13 12:16 .bashrc
drwx------ 2 alex alex 4096 Jun 24 20:42 .cache
-rw-r--r-- 1 alex alex  807 Feb 13 12:16 .profile
-rwxrwxr-x 1 alex alex    8 Jun 25 16:29 sh
-rw------- 1 alex alex  240 Jun 24 20:38 user.txt
root@haad-b6602224:/home/alex# cat root.txt
cat: root.txt: No such file or directory

root@haad-b6602224:/home/alex# cd ..

root@haad-b6602224:/home# ls
alex  nodir

root@haad-b6602224:/home# cat alex
cat: alex: Is a directory

root@haad-b6602224:/home# cat nodir
cat: nodir: Is a directory

root@haad-b6602224:/home# la -l
total 8
drwxr-x--- 3 alex  alex  4096 Jun 25 16:29 alex
drwxr-x--- 2 nodir nodir 4096 Jun 24 20:32 nodir

root@haad-b6602224:/home# ls -la
total 16
drwxr-xr-x  4 root  root  4096 Jun 24 20:38 .
drwxr-xr-x 18 root  root  4096 Jun 25 15:23 ..
drwxr-x---  3 alex  alex  4096 Jun 25 16:29 alex
drwxr-x---  2 nodir nodir 4096 Jun 24 20:32 nodir

root@haad-b6602224:/home# cd /root
root@haad-b6602224:~# ls -la
total 36
drwx------  5 root root 4096 Jun 24 20:32 .
drwxr-xr-x 18 root root 4096 Jun 25 15:23 ..
-rw-------  1 root root  277 Jun 24 20:57 .bash_history
-rw-r--r--  1 root root 3106 Apr 20 08:46 .bashrc
drwx------  2 root root 4096 Jun 24 20:21 .cache
drwxr-xr-x  3 root root 4096 Jun 24 20:21 .local
-rw-r--r--  1 root root  132 Apr 20 08:46 .profile
drwx------  2 root root 4096 Apr 29 17:23 .ssh
-rw-------  1 root root  191 Jun 24 20:38 root.txt

root@haad-b6602224:~# cat root.txt

FLAG{root_system_compromised_successfully_88301742}

Tabriklaymiz! Siz ushbu CTF mashinasini to'liq yechib chiqdingiz!
O'quvchilaringiz kiberxavfsizlik asoslarini muvaffaqiyatli o'rganishdi!
root@haad-b6602224:~#
