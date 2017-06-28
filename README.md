```
             _                  _                 
            | |                (_)                
  __ _ _   _| |_ ___  _ __ ___  _ _ __   ___ _ __ 
 / _` | | | | __/ _ \| '_ ` _ \| | '_ \ / _ \ '__|
| (_| | |_| | || (_) | | | | | | | | | |  __/ |   
 \__,_|\__,_|\__\___/|_| |_| |_|_|_| |_|\___|_|   

 A command-line utility to automatically mine the most profitable coin
```

# Overview
Autominer is a command-line utility to automatically mine the most profitable coin. It uses [WhatToMine](http://whattomine.com) to determine the most profitable coin for your system, and makes sure you're mining it.

# Features

* Mines the most profitable coin for your rig (according to [WhatToMine](http://whattomine.com))
* Supports all mining software (including Dual Miners)
* Automatically restarts your mining software if it crashes
* Does not impact hashrates (uses almost no system resources)

# Releases
The current version is **0.3.3**
* Windows: [autominer-0.3.3-windows64.zip](https://github.com/autominer/autominer/releases/download/v0.3.3/autominer-0.3.3-windows64.zip)
* Linux: [autominer-0.3.3-linux.tar.gz](https://github.com/autominer/autominer/releases/download/v0.3.3/autominer-0.3.3-linux.tar.gz)

# Setup
1. Download the latest version of autominer, and extract the files.

2. Go to [WhatToMine](http://whattomine.com), configure the hashrate/power settings for your rig, then press "Calculate"

3. Copy the resulting URL from your browser. It should look something like:

```
http://whattomine.com/coins?......
```

4. Open a terminal/command prompt, and execute autominer with the `generate-config` command, passing the WhatToMine URL as an argument.

**IMPORTANT: The URL must be wrapped in double-quotes `"..."`**

Windows:
```
autominer.exe generate-config "http://whattomine.com/coins?..."
```

Linux:
```
./autominer generate-config "http://whattomine.com/coins?..."
```

5. Open the generated `config.yml` file in a text editor, and adjust your coins/miners. You may want to create batch/shell scripts for each coin you plan to mine. You can also adjust the `profit_threshold` and `update_interval` settings to suit your needs.

Example:
```yml
# What To Mine configuration parameters (use generate-config to change)
wtmparams: "...."

# Minimum difference in profitability to switch (ex. 10 = 10% higher)
profit_threshold: 10

# Interval (in minutes) between profitability updates
update_interval: 60

# Coins to mine / command to start miner (See http://whattomine.com/coins for coin symbols)
ETH: "mine_eth.bat"
ZEC: "mine_zec.bat"

# Dual-coin profitability is also supported
ETH+DCR: "dualmine_eth_dcr.bat"
```

6. Start autominer (make sure the `config.yml` file is in the same directory as the autominer executable)

7. ?????

8. Increased profits!

# Support us
```
If this helps you, consider helping us <3

BTC: 1CBKutExWG4ZEfDHjtfVfaZVm35VDcZsQ6
ETH: 0xFF0bDD72cADD601E2F34f52479De6Ae6113F143C
ZEC: t1fvVvyou26utt1ysj1mmbFxNZUG1KvSJDn
```

