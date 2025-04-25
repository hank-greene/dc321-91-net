
$ sudo /opt/arkime/bin/Configure
[sudo] password for ellie:
Found interfaces: lo;enp2s0;wlp3s0
Semicolon ';' seperated list of interfaces to monitor [eth1] lo;enp2s0;wlp3s0
Install Elasticsearch server locally for demo, must have at least 3G of memory, NOT recommended for production use (yes or no) [no]
OpenSearch/Elasticsearch server URL [https://localhost:9200]
OpenSearch/Elasticsearch user [empty is no user]
Password to encrypt S2S and other things, don't use spaces [must create one] 65m<AetDQjgg
Arkime - Creating configuration files
Not overwriting /opt/arkime/etc/config.ini, delete and run again if update required (usually not), or edit by hand
Download GEO files? You'll need a MaxMind account https://arkime.com/faq#maxmind (yes or no) [yes] yes
Arkime - Downloading GEO files
2025-04-24 12:21:32 URL:https://www.iana.org/assignments/ipv4-address-space/ipv4-address-space.csv [22972/22972] -> "/tmp/tmp.IfQsgI5SP7" [1]
2025-04-24 12:21:33 URL:https://www.wireshark.org/download/automated/data/manuf [2913795/2913795] -> "/tmp/tmp.a74ozsQsqq" [1]

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

  