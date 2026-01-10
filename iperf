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

## Test results
