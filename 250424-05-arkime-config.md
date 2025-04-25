

$ sudo /opt/arkime/db/db.pl --esuser admin https://localhost:9200 init
Enter 6+ character OpenSearch/Elasticsearch password for admin:
It is STRONGLY recommended that you stop ALL Arkime captures and viewers before proceeding.  Use 'db.pl https://localhost:9200 backup' to backup db first.

There is 1 OpenSearch/Elasticsearch data node, if you expect more please fix first before proceeding.

This is a fresh Arkime install
Erasing
Creating
Finished



thya@thya:~$ nmap localhost
Starting Nmap 7.94SVN ( https://nmap.org ) at 2025-04-24 14:42 UTC
Nmap scan report for localhost (127.0.0.1)
Host is up (0.00014s latency).
Not shown: 998 closed tcp ports (conn-refused)
PORT     STATE SERVICE
22/tcp   open  ssh
9200/tcp open  wap-wsp

Nmap done: 1 IP address (1 host up) scanned in 0.07 seconds
thya@thya:~$ sudo /opt/arkime/bin/Configure
Found interfaces: lo;enp2s0;wlp3s0
Semicolon ';' seperated list of interfaces to monitor [eth1] enp2s0;wlp3s0
Install Elasticsearch server locally for demo, must have at least 3G of memory, NOT recommended for production use (yes or no) [no] no
OpenSearch/Elasticsearch server URL [https://localhost:9200]
OpenSearch/Elasticsearch user [empty is no user]
Password to encrypt S2S and other things, don't use spaces [must create one] 65m<AetDQjgg
Arkime - Creating configuration files
Installing sample /opt/arkime/etc/config.ini
Arkime - Installing /etc/security/limits.d/99-arkime.conf to make core and memlock unlimited
Download GEO files? You'll need a MaxMind account https://arkime.com/faq#maxmind (yes or no) [yes]
Arkime - Downloading GEO files
2025-04-24 14:44:04 URL:https://www.iana.org/assignments/ipv4-address-space/ipv4-address-space.csv [22972/22972] -> "/tmp/tmp.Xs03C1Z0o4" [1]
2025-04-24 14:44:05 URL:https://www.wireshark.org/download/automated/data/manuf [2913795/2913795] -> "/tmp/tmp.tKeO5d1bMB" [1]

Arkime - Configured - Now continue with step 4 in /opt/arkime/README.txt

 4) The Configure script can install OpenSearch/Elasticsearch for you or you can install yourself
 5) Initialize/Upgrade OpenSearch/Elasticsearch Arkime configuration
  a) If this is the first install, or want to delete all data
      /opt/arkime/db/db.pl http://ESHOST:9200 init
  b) If this is an update to an Arkime package
      /opt/arkime/db/db.pl http://ESHOST:9200 upgrade
 6) Add an admin user if a new install or after an init
      /opt/arkime/bin/arkime_add_user.sh admin "Admin User" THEPASSWORD --admin
 7) Start everything
      systemctl start arkimecapture.service
      systemctl start arkimeviewer.service
 8) Look at log files for errors
      /opt/arkime/logs/viewer.log
      /opt/arkime/logs/capture.log
 9) Visit http://arkimeHOST:8005 with your favorite browser.
      user: admin
      password: THEPASSWORD from step #6

If you want IP -> Geo/ASN to work, you need to setup a maxmind account and the geoipupdate program.
See https://arkime.com/faq#maxmind

Any configuration changes can be made to /opt/arkime/etc/config.ini
See https://arkime.com/faq#arkime-is-not-working for issues

Additional information can be found at:
  * https://arkime.com/install
  * https://arkime.com/faq
  * https://arkime.com/settings


  