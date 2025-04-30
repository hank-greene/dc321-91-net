# notes from 
https://www.digitalocean.com/community/tutorials/how-to-configure-suricata-as-an-intrusion-prevention-system-ips-on-ubuntu-20-04

## ids


## ips

# suricata signatures
$ sudo suricata -T -c /etc/suricata/suricata.yaml -v
[sudo] password for ellie:
Notice: suricata: This is Suricata version 7.0.10 RELEASE running in SYSTEM mode
Info: cpu: CPUs/cores online: 4
Info: suricata: Running suricata under test mode
Info: suricata: Setting engine mode to IDS mode by default
Info: exception-policy: master exception-policy set to: auto
Info: logopenfile: fast output device (regular) initialized: fast.log
Info: logopenfile: eve-log output device (regular) initialized: eve.json
Info: logopenfile: stats output device (regular) initialized: stats.log
Info: detect: 1 rule files processed. 42975 rules successfully loaded, 0 rules failed, 0
Info: threshold-config: Threshold config parsed: 0 rule(s) found
Info: detect: 42978 signatures processed. 1227 are IP-only rules, 4344 are inspecting packet payload, 37190 inspect application layer, 109 are decoder event only
Notice: suricata: Configuration provided was successfully loaded. Exiting.

Info: detect: 42978 signatures processed. <br>
              1227 are IP-only rules, <br>
              4344 are inspecting packet payload, <br> 
              37190 inspect application layer, <br>
              109 are decoder event only <br>


# tuning suricata
https://www.freecodecamp.org/news/home-network-security-with-suricata-raspberrypi4-python/#heading-what-did-we-learn-and-what-is-next
Holy Priceless Collection of Etruscan Snoods!, Batman. 
How do we tune Suricata to avoid this overwhelming amount of information?

sudo -i
# And a YAML linter so we can make sure our Suricata configuration files are good
apt-get install yamllint
cp -v -p  /etc/suricata/suricata.yaml /etc/suricata/suricata.yaml.orig




# 
<details>
<summary><b>tame suricata logs with logrotate </b></summary>
<pre>
# Keep a week of logs, 1 GB of size.
# Always test your config: logrotate -vdf /etc/logrotate.d/suricata
/var/log/suricata/*.log /var/log/suricata/*.json {
    daily
    maxsize 1G
    rotate 7
    missingok
    nocompress
    create
    sharedscripts
    postrotate
        systemctl restart suricata.service
    endscript
}
</pre>
</details>



# 
<details>
<summary><b>emerging threats </b></summary>
1. found here, https://rules.emergingthreats.net/OPEN_download_instructions.html <br>
2. cronjob to download emerging threats and update suricata <br>
    - https://rules.emergingthreats.net/ <br>
    - https://www.proofpoint.com/us/products/advanced-threat-protection/et-intelligence <br>
    - https://www.ipfire.org/docs/configuration/firewall/ips/rulesets <br>
3. /var/log/suricata/eve.json packs a lot of data <br>
</details>


# 
<details>
<summary><b>test surciata </b></summary>
tbd
</details>


# 
<details>
<summary><b> </b></summary>
</details>


# 
<details>
<summary><b> </b></summary>
</details>