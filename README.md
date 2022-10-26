# traffic-control-script
A simple bash scripts capable of adding delay, either inbound and outbound or both at the same time.  
traffic-control-v3.sh is able to filter how many IP/subnets you insert in the command arguments.  
As well, the script is able to introduce upload/download speed limitation.  

# Usage
At line 4, modify the network interface name based on the Linux box where you’re using it;  
If you want to limit upload/download speed on the interface, set SPEED_DOWNLOAD and SPEED_UPLOAD accordingly at lines 10,11; if not, simply set this limit above real physical speed;  

Add <x> ms of latency inbound/outbound for specific list of <ip-address[es]|subnet>  
```bash
sudo ./traffic-control-v3.sh --delay=<x> <ip-address|subnet> <ip-address|subnet> ...  
```
Add <x> ms of latency inbound for specific list of <ip-address[es]|subnet>  
```bash
sudo ./traffic-control-v3.sh --delay=<x> --incoming <ip-address|subnet> <ip-address|subnet> ...  
```
Add <x> ms of latency outbound for specific list of <ip-address[es]|subnet>  
```bash
sudo ./traffic-control-v3.sh --delay=<x> --outgoing <ip-address|subnet> <ip-address|subnet> ...  
```
Remove the latency from interface  
```bash
sudo ./traffic-control-v3.sh -r  
```
