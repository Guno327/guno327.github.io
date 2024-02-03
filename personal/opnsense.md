---
layout: default
title: OPNsense
class: personal
---
## Motivation
The place that I live in has a contract with Xfinity so we do not have a choice in our ISP. Instead we have to deal with subpar internet speeds at exorbitant prices. They also recently phased out the router managment page (10.0.0.1) in favor of their mobile app. This is all well and good except that their port forward configuration utility is highly limited and does not allow you to type in an IP address for the forward, but instead must select from a list of detected devices. This was a huge issue for me becuase the server I setup in my [homelab](/personal/homelab.html) project assigns a seperate IP for each container running in proxmox and has them configured as hidden on the network. This means that I could not forward any of the ports needed for my minecraft server. To solve this issue I decided I would need my own custom router.
## Hardware
I had been considering messing around with an OPNsense or PFsense box at somepoint and had been discussing it with one of my friends. With the completion of the [homelab](/personal/homelab.html) project I had the old PC that used to be my server lying around. The r520 I had used for that project had also come with 2 spare 1Gb NICs installed so I just stole one of them for this project. So with the networking hardware in hand and a PC that was overkill for a router I began.
## Installation
I ended up battleing the BIOS of the PC for a while because it did not want to disable secure boot for some reason. After that was delt with everything went smoothly. I configured the NIC I had stole from my other server to be the LAN and used the integrated port as the WAN. With the Xfinity modem set to bridge mode and everything all connected we had our hardline network up and running. All that was left now was the wireless.
## WiFi
I had a random wireless access point lying around that I tried to use for this project but I had misplaced the power cable and could not find it for the life of me. With this dissapointment I ran out to the local Office Depot and bought the cheapest router I could find there that supported access point mode. With that in hand an properly configured the wireless network was up and running.
## Web UI issues
The whole OPNsense setup worked very well for a few days until I went to change some firewall settings to find that the web UI was glacially slow. I am talking 3 minutes to load a single page. I suffered through this agony for a while and ended up setting up a cron job to update the firmware and restart the machine every night at 3AM. Sure enough the next day after this ran everything was back in tip top shape and I have yet to have any issue up to this point.
