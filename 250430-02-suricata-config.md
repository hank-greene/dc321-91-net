# kind of annoying this lint thing

<details>
<summary><b>today's plan </b></summary>
- [x] find magneticechos deployment, install notes<br>
&nbsp;&nbsp;&nbsp;&nbsp;    - [x] see github magneticechos.online, jWic dir<br>
&nbsp;&nbsp;&nbsp;&nbsp;    - [x] see ~/Dev/2025/0102-bbmnt/ ... <br>
- [ ] modify /etc/suricata/suricata.yaml as follows <br>
&nbsp;&nbsp;&nbsp;&nbsp;   from HOME_NET: "[192.168.0.0/16,10.0.0.0/8,172.16.0.0/12]" <br>
&nbsp;&nbsp;&nbsp;&nbsp;   to   HOME_NET: "[10.10.91.0/24]" <br>
- [ ] stop suricata <br>
- [ ] modify the HOME_NETWORK <br>
- [ ] start suricata <br>
- [ ] monitor file : only ellie is in the DMS so shouldn't see any other ips in list <br>
- [ ] deploy magneticechos onto thya, then should see allerts on 91.11 <br>
</details>

<details>
<summary><b>execute suricata.yaml update</b></summary>
<pre>
  247  sudo systemctl status suricata
  248  sudo systemctl stop suricata
  249  sudo vi /etc/suricata/suricata.yaml
  250  sudo systemctl start suricata
  251  sudo systemctl status suricata
</pre>
<pre>
Not seeing anything, not going to see anything because the other nodes are behind the fire wall.
Need to update the router to allow traffic through port 8080 on Thya, after magneticechos deployed.
</pre>
</details>


<details>
<summary><b>deploy magneticechos.online </b></summary>
<pre>
ssh ivwall@ 89.20
ssh crtp1@ 93.13
</pre>
<pre>
found magneticechos on 93.10, *.war files located there too
moving *.war files from crtp1 to mactwo, hop from ivwall 89.20 to 93.13
copy *.war files 
</pre>
<pre>
moved war files to ellie, then to thya
</pre>
<details>
<summary>crtp1 history 4 tomcat install</summary>
<pre>
93.13 tomcat install
    1  history
    2  java -version
    3  sudo update-jvaa-alternatives -l
    4  sudo update-java-alternatives -l
    5  pwd
    6  cd /opt/tomcat/logs
    7  sudo su -
    8  eixt
    9  exit
   10  history
   11  df -h
   12  ps -ef | grep java
   13  history
   14  sudo su -
   15  sudo systemctl status tomcat
   16  sudo systemctl stop tomcat

   26  df -h
   27  lsblk
   51  df -h
   52  bkls
   53  blkls
   54  df
   55  df -h

   56  fdisk -l
   57  sudo su -
   58  sudo groupadd tomcat
   59  sudo useradd -s /bin/false -g tomcat -d /opt/tomcat tomcat
   60  cd /tmp
   61  curl -O https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.76/bin/apache-tomcat-9.0.76.tar.gz
   62  sudo mkdir /opt/tomcat
   63  sudo tar xzvf apache-tomcat-9.0.76.tar.gz -C /opt/tomcat --strip-components=1
   64  cd /opt/tomcat
   65  sudo chown -RH tomcat: /opt/tomcat
   66  sudo sh -c 'chmod +x /opt/tomcat/bin/*.sh'
   67  sudo update-java-alternatives -l
   68  sudo apt-get install openjdk-8-jdk
   69  sudo update-alternatives -java
   70  sudo update-alternatives --config java
   71  java -version

   74  sudo vi /etc/systemd/system/tomcat.service
   75  sudo systemctl daemon-reload
   76  sudo systemctl start tomcat
   77  sudo systemctl status tomcat
   78  sudo ufw status
   79  sudo systemctl status ufw
   80  sudo systemctl enable ufw
   81  sudo systemctl status ufw
   82  sudo ufw allow ssh
   83  sudo ufw allow 22
   84  sudo ufw allow 8080/tcp
   85  history
   86  cd conf
   87  sudo su -
   88  sudo systemctl status tomcat
   89  sudo systemctl restart tomcat
   90  sudo systemctl status tomcat

  135  netstat -antl
  136  sudo su -
  137  history
  138  sudo su -
  139  ls -l
  140  cd Dev
  141  ls -l
  142  cd ..
  143  ls -l
  144  sudo su -
  145  exit
  146  cd /opt
  147  ls -l
  148  cd tomcat
  149  ls -l
  150  cd conf
  151  sudo su -
  152  cd ~
  153  ls -l
  154  cd Dev
  155  ls -l
  156  ip a
  157  exit
  158  history
  159  sudo systemctl status tomcat
  160  sudo systemctl stop tomcat
  161  sudo systemctl start tomcat
  162  sudo systemctl status tomcat
  163  exit
  164  java version
  165  java -version
  166  pwd
  167  ls -l
  168  cd Dev
  169  ls -l
  170  mkdir 2024
  171  cd 2024
  172  mkdir 1206-bbmnt
  173  cd 1206-bbmnt/
  174  git clone git@github.com:cf2141/bbmnt01.git
  175  cd ~
  176  ls -al
  177  cd .ssh
  178  ls -l
  179  cat id_ed25519.pub
  180  cd ..
  181  ls -l
  182  cd Dev/2024/
  183  ls -l
  184  cd 1206-bbmnt/
  185  ls -l
  186  git clone git@github.com:cf2141/bbmnt01.git
  187  ls -l
  188  cd bbmnt01/
  189  ls -l
  190  cd jWic/
  191  ls -l
  192  sudo apt install mvn
  193  sudo apt install maven -y
  194  mvn
  195  mvn package
  196  exit
  197  java -version
  198  exit
  199  ls -l
  200  cd Dev
  201  ls -l
  202  cd 2024
  203  ls -l
  204  cd 1206-bbmnt/
  205  ls -l
  206  cd bbmnt01/
  207  ls -l
  208  cd jWic/
  209  ls -l
  210  mvn package
  211  ls -l
  212  find . -n *.war
  213  find . -name *.war
  214  ps -ef | grep james
  215  ps -ef | grep java
  216  find . -name *.war
  217  cp .target-mvn/jwic-samples/samples.war /opt/tomcat/webapps/.
  218  sudo s0 - cp .target-mvn/jwic-samples/samples.war /opt/tomcat/webapps/.
  219  sudo su - cp .target-mvn/jwic-samples/samples.war /opt/tomcat/webapps/.
  220  sudo cp .target-mvn/jwic-samples/samples.war /opt/tomcat/webapps/.
  221  exit
  222  sudo su -
  223  exit
  224  cd /opt/tomcat
  225  ls -l
  226  cd conf
  227  sudo su -
  228  exit
  229  ls -l
  230  ls -l /opt/tomcat/webapps/
  231  sudo ls -l /opt/tomcat/webapps/
  232  sudo mv *.war /opt/tomcat/webapps/
  233  sudo /opt/tomcat/webapps/
  234  sudo ls -l /opt/tomcat/webapps/
  235  sudo ls -l /opt/tomcat/webapps/01-amp3s
  236  sudo ls -l /opt/tomcat/webapps/01-amp3s/01-amp3s
  237  sudo ls -l /opt/tomcat/webapps/01-amp3s/01-amp3s | wc
  238  sudo su -
  239  exit
  240  ping 10.10.93.1
  241  nslookup tgndomains.com
  242  ps -ef | grep java
  243  cd /opt/tomcat/
  244  ls -l
  245  cd logs
  246  sudo su -
  247  nmap localhost
  248  sudo apt install nmap
  249  nmap localhost
  250  wget localhost:8080/01-amp3s/01-amp3s.json
  251  pwd
  252  sudo su -
  253  sudo add-apt-repository "deb http://archive.canonical.com/ $(lsb_release -sc) partner"
  254  sudo apt update
  255  sudo apt install flashplugin-installer
  256  sudo add-apt-repository "deb http://archive.canonical.com/ $(lsb_release -sc) partner"
  257  sudo apt-get install vlc -y
  258  sudo apt install libdvdnav4 libdvdread4 gstreamer1.0-plugins-bad gstreamer1.0-plugins-ugly libdvd-pkg
  259  sudo apt install libdvdnav4 gstreamer1.0-plugins-bad gstreamer1.0-plugins-ugly libdvd-pkg
  260  sudo apt install ubuntu-restricted-extras
  261  sudo apt install libdvdnav4 libdvdread4 gstreamer1.0-plugins-bad gstreamer1.0-plugins-ugly libdvd-pkg
  262  uname -a
  263  uname -r
  264  cat /etc/os-release
  265  sudo apt-get update
  266  sudo apt-get install libdvdread4
  267  sudo apt-get install libdvdread7
  268  cat /etc/os-release
  269  sudo apt install libdvd-pkg
  270  sudo add-apt-repository multiverse
  271  sudo apt install libdvd-pkg
  272  sudo apt install libdvdread8
  273  sudo apt-get install vlc
  274  sudo reboot
  275  ls -l
  276  pwd
  277  sudo su -
  278  systemctl status tomcat
  279  systemctl start tomcat
  280  systemctl status tomcat
  281  ls -l
  282  cd Dev
  283  ls -l
  284  cd 2024
  285  ls -l
  286  cd 1206-bbmnt/
  287  ls -l
  288  cd bbmnt01/
  289  git pull
  290  git status
  291  git stash
  292  git pull
  293  ls -l
  294  cd jWic/
  295  ls -l
  296  mvn package
  297  pwd
  298  git status
  299  find . -name *.war
  300  git pull
  301  pwd
  302  ls -l
  303  mvn package
  304  git pull
  305  mvn package
  306  find . -name *.war
  307  ls -l /opt/tomcat/webapps/
  308  sudo ls -l /opt/tomcat/webapps/
  309  find . -name *.war
  310  sudo cp .target-mvn/jwic-samples/samples.war /opt/tomcat/webapps/.
  311  sudo ls -l /opt/tomcat/webapps/
  312  pwd
  313  ls -l
  314  ls -l de.jwic.samples/
  315  ls -l de.jwic.samples/src
  316  ls -l de.jwic.samples/src/de
  317  ls -l de.jwic.samples/src/de/jwic/
  318  pwd
  319  git pull
  320  mvn package
  321  sudo cp .target-mvn/jwic-samples/samples.war /opt/tomcat/webapps/.
  322  find . -name audio-test
  323  find . -name *.war
  324  ls -l .target-mvn/jwic-samples/samples.war
  325  git pull
  326  mvn package
  327  sudo cp .target-mvn/jwic-samples/samples.war /opt/tomcat/webapps/.
  328  git pull
  329  mvn package
  330  sudo cp .target-mvn/jwic-samples/samples.war /opt/tomcat/webapps/.
  331  sudo su -
  332  pwd
  333  git branch -r
  334  ls -l
  335  cd Dev/2024
  336  ls -l
  337  cd 1206-bbmnt/
  338  ls -l
  339  cd bbmnt01/
  340  ls -l
  341  git branch -r
  342  git branch -a
  343  git pull
  344  git branch -r
  345  git checkout prune01
  346  git branch -a
  347  ls -l
  348  ls -l jWic/
  349  pwd
  350  ls -l
  351  git status
  352  git restore *
  353  git status
  354  git add .
  355  git commit -m "audio-test"
  356  git push
  357  git pull
  358  git status
  359  git pull
  360  pwd
  361  sudo su -
  362  ls -l
  363  git pull
  364  cd jWic/
  365  mvn package
  366  history
  367  sudo cp .target-mvn/jwic-samples/samples.war /opt/tomcat/webapps/.
  368  git pull
  369  mvn package
  370  sudo cp .target-mvn/jwic-samples/samples.war /opt/tomcat/webapps/.
  371  ip a
  372  git pull
  373  mvn package
  374  sudo cp .target-mvn/jwic-samples/samples.war /opt/tomcat/webapps/.
  375  mvn package
  376  sudo cp .target-mvn/jwic-samples/samples.war /opt/tomcat/webapps/.
  377  git pull
  378  mvn package
  379  sudo cp .target-mvn/jwic-samples/samples.war /opt/tomcat/webapps/.
  380  sudo su -
  381  ls -l
  382  cd /opt/tomcat/
  383  ls -
  384  ls -l
  385  history | grep sudo
  386  sudo sysctl status tomcat
  387  sudo systemctl status tomcat
  388  ls -l
  389  cd bin
  390  sudo su -
  391  sudo su -
  392  ls -l
  393  cd Dev/
  394  ls -l
  395  cd ..
  396  ls -l
  397  pwd
  398  mkdir Download
  399  cd Download/
  400  wget -c https://downloads.apache.org/tomcat/tomcat-9/v9.0.34/bin/apache-tomcat-9.0.34.tar.gz
  401  wget -c https://downloads.apache.org/tomcat/tomcat-9/v9.0.98/bin/apache-tomcat-9.0.98.tar.gz
  402  ls -l
  403  gunzip apache-tomcat-9.0.98.tar.gz
  404  ls -l
  405  tar xvf apache-tomcat-9.0.98.tar
  406  ls -l
  407  cd apache-tomcat-9.0.98/
  408  ls -l
  409  cd conf
  410  ls -l
  411  cat tomcat-users.xml
  412  cp tomcat-users.xml tomcat-users.xml-9.0.98
  413  cp tomcat-users.xml-9.0.98 /opt/tomcat/conf/.
  414  sudo cp tomcat-users.xml-9.0.98 /opt/tomcat/conf/.
  415  sudo su -
  416  ping 10.10.93.20
  417  sudo su -
  418  exit
  419  cd /opt/
  420  ls -l
  421  cd tomcat/
  422  ls -l
  423  cd webapps
  424  sudo su -
  425  exit
  426  sudo su -
  427  sudo su -
  428  netstat -antlr
  429  nmap 127.0.0.1
  430  ls -l
  431  ping 10.10.93.10
  432  nmap 10.10.93.10
  433  curl http://10.10.93.10:80
  434  curl http://10.10.93.10
  435  df -h
  436  nslookup https://www.crownlimodc.com/
  437  nslookup crownlimodc.com
  438  nmap 185.230.63.171
  439  traceroute 185.230.63.171
  440  sudo apt install traceroute
  441  traceroute 185.230.63.171
  442  ls -l
  443  history
  444  df -h
  445  curl http://10.10.93.10:80
  446  sudo su -
  447  curl http://10.10.93.10:80
  448  curl http://10.10.93.10:8080
  449  sudo su -
  450  nmap
  451  nmap 173.166.130.89
  452  nmap 173.166.130.90
  453  nmap 173.166.130.91
  454  nmap 173.166.130.92
  455  nmap 173.166.130.93
  456  nmap 173.166.130.94
  457  ssh ivwall@173.166.130.93
  458  ssh 173.166.130.93
  459  telnet 173.166.130.93
  460  telnet 173.166.130.93 25
  461  exit
  462  nmap 173.166.130.93
  463  history
  464  cd /opt
  465  ls -l
  466  cd tomcat
  467  ls -l
  468  cd ~
  469  ls -l
  470  ls -l Download/
  471  ls -l Dev
  472  ls -l Dev/2024/
  473  ls -l Dev/2024/1206-bbmnt/
  474  ls -l Dev/2024/1206-bbmnt/bbmnt01/
  475  ls -l Dev/2024/1206-bbmnt/bbmnt01/jWic/
  476  find . -name *.war
  477  cd /opt/tomcat/
  478  ls -l
  479  ip a
  480  ls -l
  481  ls -l webapps
  482  sudo ls -l webapps
  483  df -h
  484  exit
  485  cd /opt/tomcat
  486  ls -l
  487  sudo ls -l webapps/*.war
  488  sudo ls -l webapps
  489  exit
  490  sudo ls -l /opt/tomcat/webapps
  491  sudo cp /opt/tomcat/webapps/01-amp3s.war .
  492  sudo cp /opt/tomcat/webapps/samples.war .
  493  ls -l
  494  chown crtp1 01-amp3s.war
  495  sudo chown crtp1 01-amp3s.war
  496  sudo chgrp crtp1 01-amp3s.war
  497  sudo chgrp crtp1 samples.war
  498  sudo chown crtp1 samples.war
  499  exit
  500  history
</pre>
</details>

<pre>
thya@thya:~$ wget -c https://downloads.apache.org/tomcat/tomcat-9/v9.0.104/bin/apache-tomcat-9.0.104.tar.gz
--2025-04-30 17:28:43--  https://downloads.apache.org/tomcat/tomcat-9/v9.0.104/bin/apache-tomcat-9.0.104.tar.gz
Resolving downloads.apache.org (downloads.apache.org)... 88.99.208.237, 135.181.214.104, 2a01:4f9:3a:2c57::2, ...
Connecting to downloads.apache.org (downloads.apache.org)|88.99.208.237|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 12787166 (12M) [application/x-gzip]
Saving to: ‘apache-tomcat-9.0.104.tar.gz’

apache-tomcat-9.0.104.tar.gz                          100%[=========================================================================================================================>]  12.19M  1.80MB/s    in 6.4s

2025-04-30 17:28:50 (1.91 MB/s) - ‘apache-tomcat-9.0.104.tar.gz’ saved [12787166/12787166]

</pre>

</details>

<details>
<summary><b>install tomcat </b></summary>
<pre>
   86  wget -c https://downloads.apache.org/tomcat/tomcat-9/v9.0.104/bin/apache-tomcat-9.0.104.tar.gz
   87  sudo mkdir /opt/tomcat
   92  sudo tar xzvf apache-tomcat-9.0.104.tar.gz -C /opt/tomcat --strip-components=1
   93  sudo groupadd tomcat
   94  sudo useradd -s /bin/false -g tomcat -d /opt/tomcat tomcat
   95  sudo chgrp -R tomcat /opt/tomcat
   96  cd /opt/tomcat
   98  sudo chmod -R g+r conf
  100  sudo chown -R tomcat webapps/ work/ temp/ logs/
  103  sudo chown -R tomcat webapps/ work/ temp/ logs/
  105  cd tomcat
  107  cd ..
  111  sudo chown -R tomcat tomcat
  114  sudo vi /etc/systemd/system/tomcat.service
  115  which java
  116  sudo vi /etc/systemd/system/tomcat.service
</pre>

</details>


<details>
<summary>create tomcat.service</summary>
<pre>
sudo vi /etc/systemd/system/tomcat.service
</pre>
<details>
<summary>tomcat.service file contents</summary>
<pre>
[Unit]
Description=Tomcat
After=network.target

[Service]
Type=forking

User=tomcat
Group=tomcat

Environment="JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk-amd64"
Environment="JAVA_OPTS=-Djava.security.egd=file:///dev/urandom -Djava.awt.headless=true"

Environment="CATALINA_BASE=/opt/tomcat"
Environment="CATALINA_HOME=/opt/tomcat"
Environment="CATALINA_PID=/opt/tomcat/temp/tomcat.pid"
Environment="CATALINA_OPTS=-Xms512M -Xmx1024M -server -XX:+UseParallelGC"

ExecStart=/opt/tomcat/bin/startup.sh
ExecStop=/opt/tomcat/bin/shutdown.sh

[Install]
WantedBy=multi-user.target
</pre>
</details>
</details>

</details>


<details>
<summary>start tomcat -- errors</summary>
<pre>
thya@thya:~$ sudo systemctl daemon-reload
[sudo] password for thya:
thya@thya:~$ sudo system status tomcat
sudo: system: command not found
thya@thya:~$ sudo systemctl status tomcat
○ tomcat.service - Tomcat
     Loaded: loaded (/etc/systemd/system/tomcat.service; disabled; preset: enabled)
     Active: inactive (dead)
thya@thya:~$ sudo systemctl start tomcat
Job for tomcat.service failed because the control process exited with error code.
See "systemctl status tomcat.service" and "journalctl -xeu tomcat.service" for details.
thya@thya:~$ sudo systemctl status tomcat
× tomcat.service - Tomcat
     Loaded: loaded (/etc/systemd/system/tomcat.service; disabled; preset: enabled)
     Active: failed (Result: exit-code) since Wed 2025-04-30 20:54:52 UTC; 7s ago
    Process: 49721 ExecStart=/opt/tomcat/bin/startup.sh (code=exited, status=1/FAILURE)
        CPU: 7ms

Apr 30 20:54:52 thya systemd[1]: Starting tomcat.service - Tomcat...
Apr 30 20:54:52 thya startup.sh[49721]: The JAVA_HOME environment variable is not defined correctly
Apr 30 20:54:52 thya startup.sh[49721]: JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk-amd64
Apr 30 20:54:52 thya startup.sh[49721]: This environment variable is needed to run this program
Apr 30 20:54:52 thya startup.sh[49721]: NB: JAVA_HOME should point to a JDK not a JRE
Apr 30 20:54:52 thya systemd[1]: tomcat.service: Control process exited, code=exited, status=1/FAILURE
Apr 30 20:54:52 thya systemd[1]: tomcat.service: Failed with result 'exit-code'.
Apr 30 20:54:52 thya systemd[1]: Failed to start tomcat.service - Tomcat.

</pre>
</details>


<details>
<summary><b>nmap check </b></summary>
<pre>
thya@thya:~$ nmap localhost
Starting Nmap 7.94SVN ( https://nmap.org ) at 2025-04-30 21:11 UTC
Nmap scan report for localhost (127.0.0.1)
Host is up (0.00012s latency).
Not shown: 998 closed tcp ports (conn-refused)
PORT     STATE SERVICE
22/tcp   open  ssh
8080/tcp open  http-proxy

Nmap done: 1 IP address (1 host up) scanned in 0.05 seconds
</pre>
</details>

<details>
<summary>ssh tunnel check</summary>
<pre>
ellie@ellie:~$ ssh -L 10.10.91.10:8080:10.10.91.11:8080 thya@10.10.91.11

From macTwo, 
</pre>
</details>

<details>
<summary><b> </b></summary>
<pre>
</pre>
My favorite search engine is [Duck Duck Go](https://duckduckgo.com "The best search engine for privacy").
</details>