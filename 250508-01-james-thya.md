# James on Thya

https://james.apache.org/server/3/install.html


https://www.apache.org/dyn/closer.lua/james/server/3.8.2/james-project-3.8.2-source-release.zip


$ wget https://dlcdn.apache.org/james/server/3.8.2/james-project-3.8.2-source-release.zip
--2025-05-08 14:23:58--  https://dlcdn.apache.org/james/server/3.8.2/james-project-3.8.2-source-release.zip
Resolving dlcdn.apache.org (dlcdn.apache.org)... 151.101.2.132, 2a04:4e42::644
Connecting to dlcdn.apache.org (dlcdn.apache.org)|151.101.2.132|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 83655366 (80M) [application/zip]
Saving to: ‘james-project-3.8.2-source-release.zip’

james-project-3.8.2-source-release.zip  100%[===============================================================================>]  79.78M  4.98MB/s    in 16s     

2025-05-08 14:24:17 (4.97 MB/s) - ‘james-project-3.8.2-source-release.zip’ saved [83655366/83655366]


https://james.apache.org/download.cgi


https://downloads.apache.org/james/server/3.8.2/james-project-3.8.2-source-release.zip.sha512



$ ls -l
total 81704
-rw-rw-r-- 1 thya thya 83655366 Jan 29 09:26 james-project-3.8.2-source-release.zip
-rw-rw-r-- 1 thya thya      833 Jan 29 09:26 james-project-3.8.2-source-release.zip.asc
-rw-rw-r-- 1 thya thya      169 Jan 29 09:26 james-project-3.8.2-source-release.zip.sha512


$ sha512sum james-project-3.8.2-source-release.zip

ea41919ad2cb5c046241ab2eae998244206fc4cae1f71cb65a50f35b75320d483bbc6015ea96de90a4dd8d2f403195426e7d1968a7098443ce3b393a5fc29218  james-project-3.8.2-source-release.zip
thya@thya:~/Downloads/250508-james$ 
thya@thya:~/Downloads/250508-james$ cat james-project-3.8.2-source-release.zip.sha512 
ea41919ad2cb5c046241ab2eae998244206fc4cae1f71cb65a50f35b75320d483bbc6015ea96de90a4dd8d2f403195426e7d1968a7098443ce3b393a5fc29218  james-project-3.8.2-source-release.zip


https://james.apache.org/server/install.html

  246  whereis update-java-alternatives
  247  update-java-alternatives --list
  248  java -version
  249  sudo update-java-alternatives --set java-1.21.0-openjdk-amd64
  250  java -version

$ java -version
openjdk version "21.0.7" 2025-04-15
OpenJDK Runtime Environment (build 21.0.7+6-Ubuntu-0ubuntu124.04)
OpenJDK 64-Bit Server VM (build 21.0.7+6-Ubuntu-0ubuntu124.04, mixed mode, sharing)


James 3.8.2 has been successfully tested on OpenJDK 11

$ sudo apt-get install openjdk-11-jdk
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following additional packages will be installed:
  openjdk-11-jdk-headless openjdk-11-jre openjdk-11-jre-headless
Suggested packages:
  openjdk-11-demo openjdk-11-source visualvm fonts-ipafont-gothic fonts-ipafont-mincho fonts-wqy-microhei | fonts-wqy-zenhei fonts-indic
The following NEW packages will be installed:
  openjdk-11-jdk openjdk-11-jdk-headless openjdk-11-jre openjdk-11-jre-headless
0 upgraded, 4 newly installed, 0 to remove and 21 not upgraded.
Need to get 119 MB of archives.
After this operation, 262 MB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://archive.ubuntu.com/ubuntu noble-updates/universe amd64 openjdk-11-jre-headless amd64 11.0.27+6~us1-0ubuntu1~24.04 [42.3 MB]
Get:2 http://archive.ubuntu.com/ubuntu noble-updates/universe amd64 openjdk-11-jre amd64 11.0.27+6~us1-0ubuntu1~24.04 [210 kB]                                 
Get:3 http://archive.ubuntu.com/ubuntu noble-updates/universe amd64 openjdk-11-jdk-headless amd64 11.0.27+6~us1-0ubuntu1~24.04 [73.7 MB]                       
Get:4 http://archive.ubuntu.com/ubuntu noble-updates/universe amd64 openjdk-11-jdk amd64 11.0.27+6~us1-0ubuntu1~24.04 [2,883 kB]                               
Fetched 119 MB in 23s (5,129 kB/s)                                                                                                                             
Selecting previously unselected package openjdk-11-jre-headless:amd64.
dpkg: warning: files list file for package 'install-info' missing; assuming package has no files currently installed
(Reading database ... 243241 files and directories currently installed.)
Preparing to unpack .../openjdk-11-jre-headless_11.0.27+6~us1-0ubuntu1~24.04_amd64.deb ...
Unpacking openjdk-11-jre-headless:amd64 (11.0.27+6~us1-0ubuntu1~24.04) ...
Selecting previously unselected package openjdk-11-jre:amd64.
Preparing to unpack .../openjdk-11-jre_11.0.27+6~us1-0ubuntu1~24.04_amd64.deb ...
Unpacking openjdk-11-jre:amd64 (11.0.27+6~us1-0ubuntu1~24.04) ...
Selecting previously unselected package openjdk-11-jdk-headless:amd64.
Preparing to unpack .../openjdk-11-jdk-headless_11.0.27+6~us1-0ubuntu1~24.04_amd64.deb ...
Unpacking openjdk-11-jdk-headless:amd64 (11.0.27+6~us1-0ubuntu1~24.04) ...
Selecting previously unselected package openjdk-11-jdk:amd64.
Preparing to unpack .../openjdk-11-jdk_11.0.27+6~us1-0ubuntu1~24.04_amd64.deb ...
Unpacking openjdk-11-jdk:amd64 (11.0.27+6~us1-0ubuntu1~24.04) ...
Setting up openjdk-11-jre-headless:amd64 (11.0.27+6~us1-0ubuntu1~24.04) ...
update-alternatives: using /usr/lib/jvm/java-11-openjdk-amd64/bin/jjs to provide /usr/bin/jjs (jjs) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-openjdk-amd64/bin/rmid to provide /usr/bin/rmid (rmid) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-openjdk-amd64/bin/pack200 to provide /usr/bin/pack200 (pack200) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-openjdk-amd64/bin/unpack200 to provide /usr/bin/unpack200 (unpack200) in auto mode
Processing triggers for desktop-file-utils (0.27-2build1) ...
Processing triggers for hicolor-icon-theme (0.17-2) ...
Processing triggers for gnome-menus (3.36.0-1.1ubuntu3) ...
Processing triggers for ca-certificates-java (20240118) ...
done.
Setting up openjdk-11-jdk-headless:amd64 (11.0.27+6~us1-0ubuntu1~24.04) ...
update-alternatives: using /usr/lib/jvm/java-11-openjdk-amd64/bin/jar to provide /usr/bin/jar (jar) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-openjdk-amd64/bin/jarsigner to provide /usr/bin/jarsigner (jarsigner) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-openjdk-amd64/bin/javac to provide /usr/bin/javac (javac) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-openjdk-amd64/bin/javadoc to provide /usr/bin/javadoc (javadoc) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-openjdk-amd64/bin/javap to provide /usr/bin/javap (javap) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-openjdk-amd64/bin/jcmd to provide /usr/bin/jcmd (jcmd) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-openjdk-amd64/bin/jdb to provide /usr/bin/jdb (jdb) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-openjdk-amd64/bin/jdeprscan to provide /usr/bin/jdeprscan (jdeprscan) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-openjdk-amd64/bin/jdeps to provide /usr/bin/jdeps (jdeps) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-openjdk-amd64/bin/jfr to provide /usr/bin/jfr (jfr) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-openjdk-amd64/bin/jimage to provide /usr/bin/jimage (jimage) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-openjdk-amd64/bin/jinfo to provide /usr/bin/jinfo (jinfo) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-openjdk-amd64/bin/jlink to provide /usr/bin/jlink (jlink) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-openjdk-amd64/bin/jmap to provide /usr/bin/jmap (jmap) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-openjdk-amd64/bin/jmod to provide /usr/bin/jmod (jmod) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-openjdk-amd64/bin/jps to provide /usr/bin/jps (jps) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-openjdk-amd64/bin/jrunscript to provide /usr/bin/jrunscript (jrunscript) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-openjdk-amd64/bin/jshell to provide /usr/bin/jshell (jshell) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-openjdk-amd64/bin/jstack to provide /usr/bin/jstack (jstack) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-openjdk-amd64/bin/jstat to provide /usr/bin/jstat (jstat) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-openjdk-amd64/bin/jstatd to provide /usr/bin/jstatd (jstatd) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-openjdk-amd64/bin/rmic to provide /usr/bin/rmic (rmic) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-openjdk-amd64/bin/serialver to provide /usr/bin/serialver (serialver) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-openjdk-amd64/bin/jaotc to provide /usr/bin/jaotc (jaotc) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-openjdk-amd64/bin/jhsdb to provide /usr/bin/jhsdb (jhsdb) in auto mode
Setting up openjdk-11-jre:amd64 (11.0.27+6~us1-0ubuntu1~24.04) ...
Setting up openjdk-11-jdk:amd64 (11.0.27+6~us1-0ubuntu1~24.04) ...
update-alternatives: using /usr/lib/jvm/java-11-openjdk-amd64/bin/jconsole to provide /usr/bin/jconsole (jconsole) in auto mode
Scanning processes...                                                                                                                                           
Scanning candidates...                                                                                                                                          
Scanning processor microcode...                                                                                                                                 
Scanning linux images...                                                                                                                                        

Pending kernel upgrade!
Running kernel version:
  6.8.0-58-generic
Diagnostics:
  The currently running kernel version is not the expected kernel version 6.8.0-59-generic.

Restarting the system to load the new kernel will not be handled automatically, so you should consider rebooting.

The processor microcode seems to be up-to-date.

No services need to be restarted.

No containers need to be restarted.

User sessions running outdated binaries:
 thya @ user manager service: gnome-session-b[2221], systemd[2058]

No VM guests are running outdated hypervisor (qemu) binaries on this host.
thya@thya:~$ update-java-alternatives --list
java-1.11.0-openjdk-amd64      1111       /usr/lib/jvm/java-1.11.0-openjdk-amd64
java-1.21.0-openjdk-amd64      2111       /usr/lib/jvm/java-1.21.0-openjdk-amd64
java-1.8.0-openjdk-amd64       1081       /usr/lib/jvm/java-1.8.0-openjdk-amd64
thya@thya:~$ sudo update-alternatives --display java-1.11.0-openjdk-amd64
update-alternatives: error: no alternatives for java-1.11.0-openjdk-amd64
thya@thya:~$ sudo update-java-alternatives --set java-1.11.0-openjdk-amd64
thya@thya:~$ java -version
openjdk version "11.0.27" 2025-04-15
OpenJDK Runtime Environment (build 11.0.27+6-post-Ubuntu-0ubuntu124.04)
OpenJDK 64-Bit Server VM (build 11.0.27+6-post-Ubuntu-0ubuntu124.04, mixed mode, sharing)
thya@thya:~$ 

https://james.apache.org/server/install.html

https://james.apache.org/server/quick-start.html


root@thya:/opt/james/bin# history | grep james
  133  cd /opt/james
  137  ./james
  138  ./james start
  140  ps -ef | grep james
  141  ./james
  142  ./james status
  144  ./james stop
  145  history | grep james


# nmap localhost
Starting Nmap 7.94SVN ( https://nmap.org ) at 2025-05-08 16:36 UTC
Nmap scan report for localhost (127.0.0.1)
Host is up (0.0000040s latency).
Not shown: 993 closed tcp ports (reset)
PORT     STATE SERVICE
22/tcp   open  ssh
25/tcp   open  smtp
110/tcp  open  pop3
143/tcp  open  imap
631/tcp  open  ipp
8080/tcp open  http-proxy
9999/tcp open  abyss

Nmap done: 1 IP address (1 host up) scanned in 0.07 seconds

# nmap localhost
Starting Nmap 7.94SVN ( https://nmap.org ) at 2025-05-08 16:36 UTC
Nmap scan report for localhost (127.0.0.1)
Host is up (0.0000040s latency).
Not shown: 993 closed tcp ports (reset)
PORT     STATE SERVICE
22/tcp   open  ssh
25/tcp   open  smtp
110/tcp  open  pop3
143/tcp  open  imap
631/tcp  open  ipp
8080/tcp open  http-proxy
9999/tcp open  abyss

Nmap done: 1 IP address (1 host up) scanned in 0.07 seconds

# ./james stop
Stopping Apache James :: Server :: Spring :: App...
Waiting for Apache James :: Server :: Spring :: App to exit...
Stopped Apache James :: Server :: Spring :: App.
root@thya:/opt/james/bin# history | grep james
  133  cd /opt/james
  137  ./james
  138  ./james start
  140  ps -ef | grep james
  141  ./james
  142  ./james status
  144  ./james stop
  145  history | grep james

