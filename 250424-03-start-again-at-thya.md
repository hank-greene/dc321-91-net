

sudo apt update default-jre

sudo vi /etc/environment
OPENSEARCH_INITIAL_ADMIN_PASSWORD=65m<AetDQjgg


$ sudo apt install ./opensearch-2.13.0-linux-x64.deb
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
Note, selecting 'opensearch' instead of './opensearch-2.13.0-linux-x64.deb'
opensearch is already the newest version (2.13.0).
0 upgraded, 0 newly installed, 0 to remove and 59 not upgraded.
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
Scanning processor microcode...
Scanning linux images...

Pending kernel upgrade!
Running kernel version:
  6.8.0-57-generic
Diagnostics:
  The currently running kernel version is not the expected kernel version 6.8.0-58-generic.

Restarting the system to load the new kernel will not be handled automatically, so you should consider rebooting.

The processor microcode seems to be up-to-date.

No services need to be restarted.

No containers need to be restarted.

No user sessions are running outdated binaries.

No VM guests are running outdated hypervisor (qemu) binaries on this host.


$ curl -k --user "admin:$OPENSEARCH_INITIAL_ADMIN_PASSWORD" https://localhost:9200/_cat/health
1745504920 14:28:40 opensearch green 1 1 true 4 4 0 0 0 0 - 100.0%

