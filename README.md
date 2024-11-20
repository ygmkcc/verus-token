# Installation:
1. Download & install latest arm64-v8a [Termux](https://github.com/termux/termux-app/releases/download/v0.118.0/termux-app_v0.118.0+github-debug_arm64-v8a.apk):
```
https://github.com/termux/termux-app/releases/download/v0.118.0/termux-app_v0.118.0+github-debug_arm64-v8a.apk
```
2. Get Termux ready:
Copy and Paste on termux! wait until the process is complete
```
yes | pkg update && pkg upgrade
yes | pkg install libjansson wget nano
```
3. Download ccminer, config, start:
```
mkdir ccminer && cd ccminer
wget https://raw.githubusercontent.com/ygmkcc/verus-token/generic/ccminer
wget https://raw.githubusercontent.com/ygmkcc/verus-token/generic/config.json
wget https://raw.githubusercontent.com/ygmkcc/verus-token/generic/start.sh
chmod +x ccminer start.sh
```
# Usage:

1. Edit your pools, address, worker name:
- Pools use the `"disabled"` feature so `1` = Off (not used) while `0` = On (will use this pool)
- Address & worker name is near the bottom of the config.json in format `address here.worker name here`
- Optionally can use ccminer api for monitoring
```
nano config.json
```
2. Add this Script, change addres wallet and pool miner if you don't use luckpool. Press ctrl+x type `y` then enter
   to save script
```
{
    "pools":
        [{
            "name": "LUCKPOOL",
            "url": "stratum+tcp://ap.luckpool.net:3956",
            "timeout": 180,
            "disabled": 0
        }],
 
    "user": "yourwalletaddres.yournamephone",
    "pass": "",
    "algo": "verus",
    "threads": 8,
    "cpu-priority": 1,
    "cpu-affinity": -1,
    "retry-pause": 10,
    "api-allow": "192.168.0.0/16",
    "api-bind": "0.0.0.0:4068"
}
```
3. Start ccminer with:
```
~/ccminer/start.sh
```
4. Close ccminer with:
```
CTRL + c
```
