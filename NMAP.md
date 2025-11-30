# 1. nmap scan

```
sudo nmap -sV -p- 192.168.138.156
```

```
Starting Nmap 7.95 ( https://nmap.org ) at 2025-11-30 09:00 +05
Nmap scan report for 192.168.138.156
Host is up (0.0044s latency).
Not shown: 65505 closed tcp ports (reset)
PORT      STATE SERVICE     VERSION
21/tcp    open  ftp         vsftpd 2.3.4
22/tcp    open  ssh         OpenSSH 4.7p1 Debian 8ubuntu1 (protocol 2.0)
23/tcp    open  telnet      Linux telnetd
25/tcp    open  smtp        Postfix smtpd
53/tcp    open  domain      ISC BIND 9.4.2
80/tcp    open  http        Apache httpd 2.2.8 ((Ubuntu) DAV/2)
111/tcp   open  rpcbind     2 (RPC #100000)
139/tcp   open  netbios-ssn Samba smbd 3.X - 4.X (workgroup: WORKGROUP)
445/tcp   open  netbios-ssn Samba smbd 3.X - 4.X (workgroup: WORKGROUP)
512/tcp   open  exec        netkit-rsh rexecd
513/tcp   open  login       OpenBSD or Solaris rlogind
514/tcp   open  tcpwrapped
1099/tcp  open  java-rmi    GNU Classpath grmiregistry
1524/tcp  open  bindshell   Metasploitable root shell
2049/tcp  open  nfs         2-4 (RPC #100003)
2121/tcp  open  ftp         ProFTPD 1.3.1
3306/tcp  open  mysql       MySQL 5.0.51a-3ubuntu5
3632/tcp  open  distccd     distccd v1 ((GNU) 4.2.4 (Ubuntu 4.2.4-1ubuntu4))
5432/tcp  open  postgresql  PostgreSQL DB 8.3.0 - 8.3.7
5900/tcp  open  vnc         VNC (protocol 3.3)
6000/tcp  open  X11         (access denied)
6667/tcp  open  irc         UnrealIRCd
6697/tcp  open  irc         UnrealIRCd
8009/tcp  open  ajp13       Apache Jserv (Protocol v1.3)
8180/tcp  open  http        Apache Tomcat/Coyote JSP engine 1.1
8787/tcp  open  drb         Ruby DRb RMI (Ruby 1.8; path /usr/lib/ruby/1.8/drb)
43896/tcp open  mountd      1-3 (RPC #100005)
50060/tcp open  nlockmgr    1-4 (RPC #100021)
53799/tcp open  status      1 (RPC #100024)
59924/tcp open  java-rmi    GNU Classpath grmiregistry
MAC Address: 00:0C:29:56:A2:68 (VMware)
Service Info: Hosts:  metasploitable.localdomain, irc.Metasploitable.LAN; OSs: Unix, Linux; CPE: cpe:/o:linux:linux_kernel

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 145.25 seconds

```

### TYPES OF SERVICES ON METASPLOITABLE2

## 1. Remote Access Services

| Port | Service | Description                                  |
| ---- | ------- | -------------------------------------------- |
| 22   | SSH     | Secure remote login (but outdated version).  |
| 23   | Telnet  | Remote login without encryption (insecure).  |
| 512  | rexec   | Remote execution service (legacy, insecure). |
| 513  | rlogin  | Older remote login protocol.                 |



## 2. File Transfer & Sharing Services

| Port    | Service       | Description                             |
| ------- | ------------- | --------------------------------------- |
| 21      | FTP (vsftpd)  | Classic file transfer protocol.         |
| 2121    | FTP (ProFTPD) | Another FTP server instance.            |
| 139/445 | Samba (SMB)   | Windows-style file sharing.             |
| 2049    | NFS           | Network File System for shared folders. |
| 43896   | mountd        | NFS mount handler.                      |


## 3. Web & Application Services

| Port | Service      | Description                          |
| ---- | ------------ | ------------------------------------ |
| 80   | Apache 2.2.8 | Main web server.                     |
| 8009 | AJP13        | Connector between Apache and Tomcat. |
| 8180 | Tomcat       | Java web application server.         |


## 4. Database Services

| Port | Service    | Description                         |
| ---- | ---------- | ----------------------------------- |
| 3306 | MySQL      | Relational database system.         |
| 5432 | PostgreSQL | Another relational database system. |


## 5. Mail & Communication Services

| Port      | Service      | Description                 |
| --------- | ------------ | --------------------------- |
| 25        | Postfix SMTP | Mail transfer service.      |
| 6667/6697 | IRC          | Internet Relay Chat server. |


## 6. Network Infrastructure Services

| Port  | Service  | Description                 |
| ----- | -------- | --------------------------- |
| 53    | BIND DNS | Domain Name System server.  |
| 111   | RPCbind  | Maps RPC services to ports. |
| 50060 | nlockmgr | NFS locking service.        |
| 53799 | status   | RPC reporting service.      |

## 7. Remote Desktop / GUI Services

| Port | Service | Description                 |
| ---- | ------- | --------------------------- |
| 5900 | VNC     | Remote desktop environment. |
| 6000 | X11     | Graphical display server.   |


## 8. Developer / Execution Services

| Port | Service  | Description                   |
| ---- | -------- | ----------------------------- |
| 3632 | distccd  | Distributed compiler service. |
| 8787 | Ruby DRb | Distributed Ruby service.     |


## 9. Java-based Services

| Port  | Service           | Description                        |
| ----- | ----------------- | ---------------------------------- |
| 1099  | Java RMI Registry | Remote method invocation registry. |
| 59924 | Java RMI Registry | Another RMI instance.              |


## 10. Special / Notable Services

| Port | Service   | Description                                |
| ---- | --------- | ------------------------------------------ |
| 1524 | bindshell | A deliberately insecure shell for testing. |

