# Troubleshooting wifi
## Test local network with iperf

On remote machine
```
pacman -S iperf3
iperf3 -s
```

On host machine
```
iperf3 -c <remote ip>
```

Test external network with iperf

On remote machine
```
pacman -c iperf.as42831.net -p 5300
```

May need to prioritize 2.4GHz band depending on physical machine locations
```
# /etc/iwd/main.conf
[Rank]
BandModifier5GHz=0.0
BandModifier2_4GHz=1.0
```

## Tests using iPerf3
``` mermaid
---
title: "Internal WiFi / LAN"
---
flowchart LR
    a@{shape: rect, label: "MacBook Client"}
    b@{shape: rect, label: "Router"}
    c@{shape: rect, label: "iMac Server"}
    a-- WiFi -->b
    b-- LAN -->c
```
``` mermaid
---
title: "Internal WiFi"
---
flowchart LR
    a@{shape: rect, label: "MacBook Client"}
    b@{shape: rect, label: "Router"}
    c@{shape: rect, label: "iMac Server"}
    a-- WiFi -->b
    b-- WiFi -->c
```
``` mermaid
---
title: "External WiFi / LAN"
---
flowchart LR
    a@{shape: rect, label: "MacBook Client"}
    b@{shape: rect, label: "Router"}
    d@{shape: rect, label: "External iPerf Server"}
    a-- WiFi -->b
    b-- LAN -->d
```
``` mermaid
---
title: "External LAN"
---
flowchart LR
    b@{shape: rect, label: "Router"}
    c@{shape: rect, label: "iMac Client"}
    d@{shape: rect, label: "External iPerf Server"}
    c-- LAN -->b
    b-- LAN -->d
```
