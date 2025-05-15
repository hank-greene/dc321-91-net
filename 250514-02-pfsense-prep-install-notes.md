
# pfsense HA
https://docs.netgate.com/pfsense/en/latest/recipes/high-availability.html

# OpenVPN notes
https://docs.netgate.com/pfsense/en/latest/recipes/openvpn-ra.html

# pfsense flash dirve install
https://netosec.com/install-pfsense-flash-drive/

# there internet says KVM introduces complexities to pfsense 
# and that makes sense, so bare metel here we go

# pfsense images
https://repo.ialab.dsu.edu/pfsense/
https://atxfiles.netgate.com/mirror/downloads/



# ...
tr9210 > ls -l
total 1147320
-rw-r--r--@ 1 tr9210  staff         36 May 13 13:19 download-location.txt
drwxr-xr-x@ 5 tr9210  staff        160 May 14 09:36 not-used
-rw-r--r--@ 1 tr9210  staff        114 May 13 13:18 pfSense-CE-2.7.2-RELEASE-amd64.iso.gz.sha256
-rw-r--r--@ 1 tr9210  staff  576633377 May 14 09:33 pfSense-CE-memstick-2.7.2-RELEASE-amd64.img.gz
-rw-r--r--@ 1 tr9210  staff        123 May 14 09:35 pfSense-CE-memstick-2.7.2-RELEASE-amd64.img.gz.sha256
tr9210 > mv pfSense-CE-2.7.2-RELEASE-amd64.iso.gz.sha256 not-used

tr9210 > shasum -a 256 pfSense-CE-memstick-2.7.2-RELEASE-amd64.img.gz
7c68b40c02f06f17146e2f1d5899e2f4a2bcfd98803f06fef8ecf3e2d0f63dcb  pfSense-CE-memstick-2.7.2-RELEASE-amd64.img.gz


tr9210 > cat pfSense-CE-memstick-2.7.2-RELEASE-amd64.img.gz.sha256
SHA256 (pfSense-CE-memstick-2.7.2-RELEASE-amd64.img.gz) = 

77c68b40c02f06f17146e2f1d5899e2f4a2bcfd98803f06fef8ecf3e2d0f63dcb

