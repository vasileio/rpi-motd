
# rpi-motd
A ***Message of the Day*** for my Raspberry Pi home server for my Raspberry Pi home server
![Untitled 2](https://user-images.githubusercontent.com/10380438/114521297-3370d180-9c3a-11eb-8c7d-e555e3c901e5.jpg)
## Installation:

    sudo mkdir /etc/update-motd.d/
    cp update-motd.d/* /etc/update-motd.d/
    
Schedule a cron job, by entering `crontab -e` and adding the following line:

```
0 */8 * * * sudo apt-get update >/dev/null; sudo apt-get upgrade -u -s | grep -P "^Inst" | wc -l > /etc/update-motd.d/available_updates.log
```

