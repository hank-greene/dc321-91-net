
~~https://www.atlantic.net/dedicated-server-hosting/how-to-install-arkime-moloch-packet-capture-tool-on-ubuntu-22-04/~~



pdee@pdee:~$ sudo systemctl enable --now arkimecapture
Created symlink /etc/systemd/system/multi-user.target.wants/arkimecapture.service → /etc/systemd/system/arkimecapture.service.
pdee@pdee:~$ sudo systemctl enable --now arkimeviewer
Created symlink /etc/systemd/system/multi-user.target.wants/arkimeviewer.service → /etc/systemd/system/arkimeviewer.service.
pdee@pdee:~$ systemctl status arkimecapture arkimeviewer
● arkimecapture.service - Arkime Capture
     Loaded: loaded (/etc/systemd/system/arkimecapture.service; enabled; preset: enabled)
     Active: active (running) since Fri 2025-04-25 11:59:34 UTC; 41s ago
   Main PID: 10626 (sh)
      Tasks: 7 (limit: 9323)
     Memory: 321.7M (peak: 322.2M)
        CPU: 341ms
     CGroup: /system.slice/arkimecapture.service
             ├─10626 /bin/sh -c "/opt/arkime/bin/capture -c /opt/arkime/etc/config.ini  >> /opt/arkime/logs/capture.log 2>&1"
             └─10627 /opt/arkime/bin/capture -c /opt/arkime/etc/config.ini

Apr 25 11:59:34 pdee systemd[1]: Starting arkimecapture.service - Arkime Capture...
Apr 25 11:59:34 pdee systemd[1]: Started arkimecapture.service - Arkime Capture.
Apr 25 11:59:34 pdee (sh)[10626]: arkimecapture.service: Referenced but unset environment variable evaluates to an empty string: OPTIONS

● arkimeviewer.service - Arkime Viewer
     Loaded: loaded (/etc/systemd/system/arkimeviewer.service; enabled; preset: enabled)
     Active: active (running) since Fri 2025-04-25 11:59:48 UTC; 28s ago
   Main PID: 10694 (sh)
      Tasks: 12 (limit: 9323)
     Memory: 66.1M (peak: 102.5M)
        CPU: 2.241s






