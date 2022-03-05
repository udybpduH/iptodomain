### Debian

Set user's cache credentials
```sh
sudo -v
```

Install python
```sh
sudo apt update && sudo apt install -y --no-install-recommends --no-install-suggests python3
```

Check python version
```sh
python3 -V
```

Download script only (alternative)
```
sudo apt install -y curl
curl -fsSL https://raw.githubusercontent.com/udybpduH/iptodomain/main/iptodomain.py > iptodomain.py
```

Download script repo
```sh
sudo apt install -y git
git clone https://github.com/jevalenciap/iptodomain.git
cd iptodomain
```

Copy script to `PATH` folder
```sh
sudo cp iptodomain.py /usr/bin/iptodomain
sudo chmod 550 /usr/bin/iptodomain
sudo chown $(whoami) /usr/bin/iptodomain
```

Set API key ENV (`IMPORTANT!`)
If you don't have key see [how to get it](https://spy-soft.net/virustotal-api/  #_API_Key_VirusTotal)
Common key have quotas (Request rate: `4 lookups / min` )
```sh
API_KEY="virustotal_api_key"
```

Install auxiliary soft (for resolve fqdn)
```
sudo apt install -y dnsutils
```

Get test ip
```
dig +short ya.ru > iprange.txt
```

Get history
```sh
iptodomain -a $API_KEY -f iprange.txt -o results.txt
```

All results in file `results.txt`, also promt throught STDOUT
