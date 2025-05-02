DNS issues
not resolving to open dns servers - sort of.  nslookup giving local gateway 192.168.1.1.  But opendns stats show a lot of traffic.  Do I need to be concerned with this?


dns unbound, for local lookups
opendns for external and also filter.  Turned on filter for adult sites and illegal activities

-set up dns updater on a device that lives on my netwwork full time, so opendns can always get my updated public IP
-for this create a config or setup section

-also creat a section that talks about specific issues that I ran into

-and reference resources
  -opnsense forum:   https://forum.opnsense.org/index.php?topic=30284.0
  -https://docs.opnsense.org/manual/unbound.html
  -reddit:   https://www.reddit.com/r/opnsense/comments/15d9uc2/opendns_not_working/?rdt=48225
  -Leak Test:   https://www.dnsleaktest.com
  -https://forum.opnsense.org/index.php?topic=42742.0

