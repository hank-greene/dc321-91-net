# arkime install
https://arkime.com/install

https://arkime.com/install#install-and-configure-opensearch

export OPENSEARCH_INITIAL_ADMIN_PASSWORD="PleaseChangeM3!"

export OPENSEARCH_INITIAL_ADMIN_PASSWORD="G30rg3W@sh1ngt0n"


ellie@ellie:~$ sudo apt install ./opensearch-2.13.0-linux-x64.deb
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
Note, selecting 'opensearch' instead of './opensearch-2.13.0-linux-x64.deb'
opensearch is already the newest version (2.13.0).
0 upgraded, 0 newly installed, 0 to remove and 5 not upgraded.
1 not fully installed or removed.
After this operation, 0 B of additional disk space will be used.
Do you want to continue? [Y/n] y
Setting up opensearch (2.13.0) ...
Running OpenSearch Post-Installation Script
chown: warning: '.' should be ':': ‘opensearch.opensearch’
chown: warning: '.' should be ':': ‘opensearch.adm’
chown: warning: '.' should be ':': ‘opensearch.opensearch’
chown: warning: '.' should be ':': ‘opensearch.opensearch’
### NOT starting on installation, please execute the following statements to configure opensearch service to start automatically using systemd
 sudo systemctl daemon-reload
 sudo systemctl enable opensearch.service
### You can start opensearch service by executing
 sudo systemctl start opensearch.service
### Create opensearch demo certificates in /etc/opensearch/
 See demo certs creation log in /var/log/opensearch/install_demo_configuration.log
### Breaking change in packaging since 2.13.0
 In 2.13.0 and later releases of OpenSearch, we have changed the permissions associated with access to installed files
 If you are configuring tools that require read access to the OpenSearch configuration files, we recommend you add the user that runs these tools to the 'opensearch' group
 For more information, see https://github.com/opensearch-project/opensearch-build/pull/4043
Processing triggers for libc-bin (2.39-0ubuntu8.4) ...
Scanning processes...
Scanning candidates...
Scanning processor microcode...
Scanning linux images...

Pending kernel upgrade!
Running kernel version:
  6.8.0-57-generic
Diagnostics:
  The currently running kernel version is not the expected kernel version 6.8.0-58-generic.

Restarting the system to load the new kernel will not be handled automatically, so you should consider rebooting.

The processor microcode seems to be up-to-date.

Restarting services...

Service restarts being deferred:
 /etc/needrestart/restart.d/dbus.service
 systemctl restart systemd-logind.service
 systemctl restart unattended-upgrades.service
 systemctl restart wpa_supplicant.service

No containers need to be restarted.

No user sessions are running outdated binaries.

No VM guests are running outdated hypervisor (qemu) binaries on this host.





ellie@ellie:~$ sudo systemctl daemon-reload
ellie@ellie:~$ sudo systemctl enable opensearch.service
Synchronizing state of opensearch.service with SysV service script with /usr/lib/systemd/systemd-sysv-install.
Executing: /usr/lib/systemd/systemd-sysv-install enable opensearch
Created symlink /etc/systemd/system/multi-user.target.wants/opensearch.service → /usr/lib/systemd/system/opensearch.service.
ellie@ellie:~$ sudo systemctl start opensearch.service
ellie@ellie:~$ sudo systemctl status opensearch.service
● opensearch.service - OpenSearch
     Loaded: loaded (/usr/lib/systemd/system/opensearch.service; enabled; preset: enabled)
     Active: active (running) since Wed 2025-04-23 20:09:40 UTC; 10s ago
       Docs: https://opensearch.org/
   Main PID: 57294 (java)
      Tasks: 86 (limit: 28604)
     Memory: 1.3G (peak: 1.3G)
        CPU: 48.940s
     CGroup: /system.slice/opensearch.service
             └─57294 /usr/share/opensearch/jdk/bin/java -Xshare:auto -Dopensearch.networkaddress.cache.ttl=60 -Dopensearch.networkaddress.cache.>

Apr 23 20:09:24 ellie systemd-entrypoint[57294]: WARNING: System::setSecurityManager has been called by org.opensearch.bootstrap.OpenSearch (fil>
Apr 23 20:09:24 ellie systemd-entrypoint[57294]: WARNING: Please consider reporting this to the maintainers of org.opensearch.bootstrap.OpenSear>
Apr 23 20:09:24 ellie systemd-entrypoint[57294]: WARNING: System::setSecurityManager will be removed in a future release
Apr 23 20:09:24 ellie systemd-entrypoint[57294]: Apr 23, 2025 8:09:24 PM sun.util.locale.provider.LocaleProviderAdapter <clinit>
Apr 23 20:09:24 ellie systemd-entrypoint[57294]: WARNING: COMPAT locale provider will be removed in a future release
Apr 23 20:09:25 ellie systemd-entrypoint[57294]: WARNING: A terminally deprecated method in java.lang.System has been called
Apr 23 20:09:25 ellie systemd-entrypoint[57294]: WARNING: System::setSecurityManager has been called by org.opensearch.bootstrap.Security (file:>
Apr 23 20:09:25 ellie systemd-entrypoint[57294]: WARNING: Please consider reporting this to the maintainers of org.opensearch.bootstrap.Security
Apr 23 20:09:25 ellie systemd-entrypoint[57294]: WARNING: System::setSecurityManager will be removed in a future release
Apr 23 20:09:40 ellie systemd[1]: Started opensearch.service - OpenSearch.





ellie@ellie:~$ sudo systemctl restart opensearch.service
ellie@ellie:~$ sudo systemctl status opensearch.service
● opensearch.service - OpenSearch
     Loaded: loaded (/usr/lib/systemd/system/opensearch.service; enabled; preset: enabled)
     Active: active (running) since Wed 2025-04-23 20:29:58 UTC; 18s ago
       Docs: https://opensearch.org/
   Main PID: 58354 (java)
      Tasks: 78 (limit: 28604)
     Memory: 1.3G (peak: 1.3G)
        CPU: 43.578s
     CGroup: /system.slice/opensearch.service
             └─58354 /usr/share/opensearch/jdk/bin/java -Xshare:auto -Dopensearch.networkaddress.cache.ttl=60 -Dopensearch.networkaddress.cache.>

Apr 23 20:29:45 ellie systemd-entrypoint[58354]: WARNING: System::setSecurityManager has been called by org.opensearch.bootstrap.OpenSearch (fil>
Apr 23 20:29:45 ellie systemd-entrypoint[58354]: WARNING: Please consider reporting this to the maintainers of org.opensearch.bootstrap.OpenSear>
Apr 23 20:29:45 ellie systemd-entrypoint[58354]: WARNING: System::setSecurityManager will be removed in a future release
Apr 23 20:29:46 ellie systemd-entrypoint[58354]: Apr 23, 2025 8:29:46 PM sun.util.locale.provider.LocaleProviderAdapter <clinit>
Apr 23 20:29:46 ellie systemd-entrypoint[58354]: WARNING: COMPAT locale provider will be removed in a future release
Apr 23 20:29:46 ellie systemd-entrypoint[58354]: WARNING: A terminally deprecated method in java.lang.System has been called
lines 1-17...skipping...
● opensearch.service - OpenSearch
     Loaded: loaded (/usr/lib/systemd/system/opensearch.service; enabled; preset: enabled)
     Active: active (running) since Wed 2025-04-23 20:29:58 UTC; 18s ago
       Docs: https://opensearch.org/
   Main PID: 58354 (java)
      Tasks: 78 (limit: 28604)
     Memory: 1.3G (peak: 1.3G)
        CPU: 43.578s
     CGroup: /system.slice/opensearch.service
             └─58354 /usr/share/opensearch/jdk/bin/java -Xshare:auto -Dopensearch.networkaddress.cache.ttl=60 -Dopensearch.networkaddress.cache.>

Apr 23 20:29:45 ellie systemd-entrypoint[58354]: WARNING: System::setSecurityManager has been called by org.opensearch.bootstrap.OpenSearch (fil>
Apr 23 20:29:45 ellie systemd-entrypoint[58354]: WARNING: Please consider reporting this to the maintainers of org.opensearch.bootstrap.OpenSear>
Apr 23 20:29:45 ellie systemd-entrypoint[58354]: WARNING: System::setSecurityManager will be removed in a future release
Apr 23 20:29:46 ellie systemd-entrypoint[58354]: Apr 23, 2025 8:29:46 PM sun.util.locale.provider.LocaleProviderAdapter <clinit>
Apr 23 20:29:46 ellie systemd-entrypoint[58354]: WARNING: COMPAT locale provider will be removed in a future release
Apr 23 20:29:46 ellie systemd-entrypoint[58354]: WARNING: A terminally deprecated method in java.lang.System has been called
Apr 23 20:29:46 ellie systemd-entrypoint[58354]: WARNING: System::setSecurityManager has been called by org.opensearch.bootstrap.Security (file:>
Apr 23 20:29:46 ellie systemd-entrypoint[58354]: WARNING: Please consider reporting this to the maintainers of org.opensearch.bootstrap.Security
Apr 23 20:29:46 ellie systemd-entrypoint[58354]: WARNING: System::setSecurityManager will be removed in a future release
lin


