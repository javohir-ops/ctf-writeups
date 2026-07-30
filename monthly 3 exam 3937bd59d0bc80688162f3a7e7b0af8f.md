# monthly 3 exam

Status: Not started

### . Operation Foothold: First Steps

Siz
 pentest davomida nishon tizimga 'player' foydalanuvchisi sifatida 
dastlabki kirish oldingiz. Uy katalogingizni o'rganing va sizni 
kutayotgan dastlabki brifing faylini o'qing. Flag formati: LB{...}

Credentials

Usernameplayer

PasswordPlayer123!

Hint

cd ~ va ls buyruqlaridan foydalaning|notes katalogidagi welcome.txt faylini cat bilan o'qing

player@haad-6a1ab74e:~$cd ~
player@haad-6a1ab74e:~$ ls
data  notes  projects
player@haad-6a1ab74e:~$cd notes
player@haad-6a1ab74e:~/notes$ ls
welcome.txt
player@haad-6a1ab74e:~/notes$ cat welcome.txt
=== OPERATION FOOTHOLD - Field Notes ===
You have gained initial access to the target system as the user 'player'.
Your task: enumerate this machine using core Linux skills and recover
all the intelligence (flags) scattered across the filesystem.

Every flag has the format:  LB{...}

Start simple. You are reading this file, which means you can already
navigate directories and read files.

FLAG (Challenge 01): LB{welcome_to_the_shell}

Tip: not everything is where you can see it. Some files are hidden.

2

### 2. Hidden in Plain Sight

Nishon tizimda hamma narsa ham ko'rinib turmaydi. Uy katalogingizdagi yashirin fayllarni toping va ular ichidagi flagni oling.

Credentials

Usernameplayer

PasswordPlayer123!

Hint

Yashirin fayllar nuqta (.) bilan boshlanadi|ls -la barcha yashirin fayllarni ko'rsatadi

player@haad-6a1ab74e:~/notes$ cd ~
player@haad-6a1ab74e:~$ls -a
.  ..  .bash_history  .bash_logout  .bashrc  .cache  .profile  .secret_flag  data  notes  projects
player@haad-6a1ab74e:~$ cat .secret_flag
Well done. Hidden files begin with a dot (.) and are revealed with `ls -la`.
FLAG (Challenge 02): LB{hidden_in_plain_sight}

3

### 3. Leaky Environment

Ba'zi
 dasturlar maxfiy tokenlarni muhit o'zgaruvchilarida (environment 
variables) yoki shell start-up fayllarida saqlaydi. Sizning shell 
muhitingizda joylashtirilgan token flagini toping.

Credentials

Usernameplayer

PasswordPlayer123!

Hint

echo $VARIABLE bilan o'zgaruvchi qiymatini ko'ring|~/.bashrc faylini o'qing yoki COMPANY_TOKEN o'zgaruvchisini echo qiling

player@haad-6a1ab74e:~$ env
SHELL=/bin/bash
COLORTERM=truecolor
PWD=/home/player
LOGNAME=player
XDG_SESSION_TYPE=tty
HOME=/home/player
LANG=C.UTF-8
LS_COLORS=rs=0:di=01;34:ln=01;36:mh=00:pi=40;33:so=01;35:do=01;35:bd=40;33;01:cd=40;33;01:or=40;31;01:mi=00:su=37;41:sg=30;43:ca=00:tw=30;42:ow=34;42:st=37;44:ex=01;32:*.tar=01;31:*.tgz=01;31:*.arc=01;31:*.arj=01;31:*.taz=01;31:*.lha=01;31:*.lz4=01;31:*.lzh=01;31:*.lzma=01;31:*.tlz=01;31:*.txz=01;31:*.tzo=01;31:*.t7z=01;31:*.zip=01;31:*.z=01;31:*.dz=01;31:*.gz=01;31:*.lrz=01;31:*.lz=01;31:*.lzo=01;31:*.xz=01;31:*.zst=01;31:*.tzst=01;31:*.bz2=01;31:*.bz=01;31:*.tbz=01;31:*.tbz2=01;31:*.tz=01;31:*.deb=01;31:*.rpm=01;31:*.jar=01;31:*.war=01;31:*.ear=01;31:*.sar=01;31:*.rar=01;31:*.alz=01;31:*.ace=01;31:*.zoo=01;31:*.cpio=01;31:*.7z=01;31:*.rz=01;31:*.cab=01;31:*.wim=01;31:*.swm=01;31:*.dwm=01;31:*.esd=01;31:*.avif=01;35:*.jpg=01;35:*.jpeg=01;35:*.mjpg=01;35:*.mjpeg=01;35:*.gif=01;35:*.bmp=01;35:*.pbm=01;35:*.pgm=01;35:*.ppm=01;35:*.tga=01;35:*.xbm=01;35:*.xpm=01;35:*.tif=01;35:*.tiff=01;35:*.png=01;35:*.svg=01;35:*.svgz=01;35:*.mng=01;35:*.pcx=01;35:*.mov=01;35:*.mpg=01;35:*.mpeg=01;35:*.m2v=01;35:*.mkv=01;35:*.webm=01;35:*.webp=01;35:*.ogm=01;35:*.mp4=01;35:*.m4v=01;35:*.mp4v=01;35:*.vob=01;35:*.qt=01;35:*.nuv=01;35:*.wmv=01;35:*.asf=01;35:*.rm=01;35:*.rmvb=01;35:*.flc=01;35:*.avi=01;35:*.fli=01;35:*.flv=01;35:*.gl=01;35:*.dl=01;35:*.xcf=01;35:*.xwd=01;35:*.yuv=01;35:*.cgm=01;35:*.emf=01;35:*.ogv=01;35:*.ogx=01;35:*.aac=00;36:*.au=00;36:*.flac=00;36:*.m4a=00;36:*.mid=00;36:*.midi=00;36:*.mka=00;36:*.mp3=00;36:*.mpc=00;36:*.ogg=00;36:*.ra=00;36:*.wav=00;36:*.oga=00;36:*.opus=00;36:*.spx=00;36:*.xspf=00;36:*~=00;90:*#=00;90:*.bak=00;90:*.old=00;90:*.orig=00;90:*.part=00;90:*.rej=00;90:*.swp=00;90:*.tmp=00;90:*.dpkg-dist=00;90:*.dpkg-old=00;90:*.ucf-dist=00;90:*.ucf-new=00;90:*.ucf-old=00;90:*.rpmnew=00;90:*.rpmorig=00;90:*.rpmsave=00;90:
SSH_CONNECTION=10.15.0.1 40184 10.15.1.200 22
LESSCLOSE=/usr/bin/lesspipe %s %s
XDG_SESSION_CLASS=user
TERM=xterm-256color
LESSOPEN=| /usr/bin/lesspipe %s
USER=player
SHLVL=1
XDG_SESSION_ID=c1
XDG_RUNTIME_DIR=/run/user/1000
SSH_CLIENT=10.15.0.1 40184 22
PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin
DBUS_SESSION_BUS_ADDRESS=unix:path=/run/user/1000/bus
SSH_TTY=/dev/pts/3
COMPANY_TOKEN=LB{env_variables_leak_secrets}
OLDPWD=/home/player
_=/usr/bin/env

4

### . Needle in the Filesystem

Tizimda chuqur ko'milgan 'hidden_key.txt' nomli fayl bor. Butun fayl tizimidan uni rekursiv qidirib toping va tarkibini o'qing.

Credentials

Usernameplayer

PasswordPlayer123!

Hint

find buyrug'i fayllarni rekursiv qidiradi|find / -name hidden_key.txt 2>/dev/null

player@haad-6a1ab74e:~$find / -name hidden_key.txt 2>/dev/null
/home/player/projects/webapp/config/.deep/hidden_key.txt
player@haad-6a1ab74e:~$ cat /home/player/projects/webapp/config/.deep/hidden_key.txt
FLAG (Challenge 04): LB{find_is_your_best_friend}

5

### 5. The Right Line

~/data/bigfile.txt
 faylida 1000 qator bor, lekin flag aynan 777-qatorda joylashgan. head 
va tail buyruqlarini birlashtirib o'sha qatorni chiqaring.

Credentials

Usernameplayer

PasswordPlayer123!

Hint

head -n 777 fayl | tail -1|head faylning boshidan, tail oxiridan qator chiqaradi

player@haad-6a1ab74e:~$ls
data  notes  projects
player@haad-6a1ab74e:~$ cd data
player@haad-6a1ab74e:~/data$ ls
access.log  bigfile.txt  employees.csv  ports.txt
player@haad-6a1ab74e:~/data$ cd bigfile.txt
-bash: cd: bigfile.txt: Not a directory
player@haad-6a1ab74e:~/data$ cat bigfile.txt

6

### 6. Grep the Needle

~/data/access.log juda katta web-server log fayli. Uning ichidan yashirin SECRET_FLAG yozuvini grep yordamida toping.

Credentials

Usernameplayer

PasswordPlayer123!

Hint

grep berilgan matnni fayldan qidiradi|grep SECRET_FLAG ~/data/access.log yoki grep 'LB{' access.log

player@haad-6a1ab74e:~$cd ~
player@haad-6a1ab74e:~$ ls
data  notes  projects
player@haad-6a1ab74e:~$grep 'LB\{' ~/data/access.log
grep: Unmatched \{
player@haad-6a1ab74e:~$ grep 'LB{' ~/data/access.log
127.0.0.1 - - [access] SECRET_FLAG=LB{grep_finds_the_needle} GET /admin HTTP/1.1 200

7

### 7. Pipe and Sort

~/data/ports.txt
 faylida minglab yozuv bor. Flag esa faylda aynan ikki marta 
takrorlangan yagona qatordir. Piping va sort/uniq yordamida takrorlangan
 qatorni toping.

Credentials

Usernameplayer

PasswordPlayer123!

Hint

sort faylni tartiblaydi, uniq -d faqat takrorlangan qatorlarni ko'rsatadi|sort ~/data/ports.txt | uniq -d

player@haad-6a1ab74e:~$ sort  ~/data/ports.txt | uniq -d
LB{count_with_wc_pipe}

8

### . Cut the Field

~/data/employees.csv
 fayli ikki nuqta (:) bilan ajratilgan maydonlardan iborat (/etc/passwd 
formatida). 'admin' foydalanuvchisining 5-maydonini (comment) ajratib 
oling.

Credentials

Usernameplayer

PasswordPlayer123!

Hint

cut -d ':' -f 5 maydonni ajratadi|grep '^admin' employees.csv | cut -d: -f5

player@haad-6a1ab74e:~$cd
player@haad-6a1ab74e:~$ ls
data  notes  projects
player@haad-6a1ab74e:~$cd data
player@haad-6a1ab74e:~/data$ ls
access.log  bigfile.txt  employees.csv  ports.txt
player@haad-6a1ab74e:~/data$ grep '^admin' employees.csv | cut -d: -f5
LB{cut_the_field_out}

9

### 9. Cron Runs as Root

Tizimda
 rejalashtirilgan (cron) vazifalar bor. /etc/cron.d ichidagi backup 
vazifasini o'rganing, u chaqirayotgan skriptni toping va ichidagi flagni
 oling.

Credentials

Usernameplayer

PasswordPlayer123!

Hint

/etc/cron.d/ katalogidagi fayllarni o'qing|cron chaqirayotgan /opt/scripts/backup.sh skriptini cat qiling

player@haad-6a1ab74e:~$ls -la /etc/cron.d/
total 24
drwxr-xr-x  2 root root 4096 Jul  3 08:08 .
drwxr-xr-x 79 root root 4096 Jul  4 14:20 ..
-rw-r--r--  1 root root  102 Nov  5  2025 .placeholder
-rw-r--r--  1 root root   76 Jul  3 08:07 backup
-rw-r--r--  1 root root  188 Jul  3 08:03 e2scrub_all
-rw-r--r--  1 root root   85 Jul  3 08:08 maintenance
player@haad-6a1ab74e:~$ cat /opt/scripts/backup.sh
#!/bin/bash

# Daily backup routine executed by cron as root.

# NOTE: rotate credentials monthly.

# FLAG (Challenge 09): LB{cron_runs_as_root}

tar -czf /var/backups/home.tgz /home 2>/dev/null

10

### 0. Logs Never Forget

Autentifikatsiya
 loglari barcha kirish urinishlarini saqlaydi. /var/log/exam/auth.log 
faylidan muvaffaqiyatli kirish (Accepted password) yozuvini toping - 
unda token bor.

Credentials

Usernameplayer

PasswordPlayer123!

Hint

grep Accepted /var/log/exam/auth.log|Muvaffaqiyatli login yozuvida token=LB{...} bor

player@haad-6a1ab74e:~$ grep Accepted /var/log/exam/auth.log
Jul  3 08:07:58 host sshd[1337]: Accepted password for operator from 10.15.1.5 port 22 ssh2 token=LB{logs_never_forget}

11

### 11. SUID Escalation

Tizimda
 root egaligidagi setuid (SUID) bajariluvchi fayl bor. Uni topib ishga 
tushiring - u sizning huquqingizdan qat'i nazar root faylini o'qiydi va 
flagni beradi.

Credentials

Usernameplayer

PasswordPlayer123!

Hint

find / -perm -4000 2>/dev/null bilan SUID fayllarni qidiring|/usr/local/bin/flagreader ni ishga tushiring

player@haad-6a1ab74e:~$cd ~
player@haad-6a1ab74e:~$ cat /etc/passwd
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
player:x:1000:1000::/home/player:/bin/bash
player@haad-6a1ab74e:~$find / -perm -4000 2>/dev/null 
/usr/bin/gpasswd
/usr/bin/sudo.ws
/usr/bin/mount
/usr/bin/su
/usr/bin/ntfs-3g
/usr/bin/umount
/usr/bin/fusermount3
/usr/bin/passwd
/usr/bin/chsh
/usr/bin/chfn
/usr/lib/openssh/ssh-keysign
/usr/lib/dbus-1.0/dbus-daemon-launch-helper
/usr/lib/cargo/bin/su
/usr/lib/cargo/bin/sudo
/usr/local/bin/flagreader
player@haad-6a1ab74e:~$ /usr/local/bin/flagreader
LB{suid_root_escalation}

12

### 12. Sudo Misconfiguration

Administrator
 sizga sudo orqali ma'lum bir buyruqni parolsiz bajarish huquqini berib 
qo'ygan. Ruxsat berilgan buyruqlarni tekshiring va undan foydalanib root
 faylini o'qing.

Credentials

Usernameplayer

PasswordPlayer123!

Hint

sudo -l joriy foydalanuvchi uchun ruxsat berilgan buyruqlarni ko'rsatadi|sudo cat /root/flag_h2.txt (parolsiz ishlaydi)

player@haad-6a1ab74e:~$sudo -l
User player may run the following commands on haad-6a1ab74e:
    (root) NOPASSWD: /usr/bin/cat /root/flag_h2.txt
player@haad-6a1ab74e:~$ sudo cat /root/flag_h2.txt
LB{sudo_misconfig_pwned}