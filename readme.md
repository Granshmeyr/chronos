# Useful Resources

**Connection Forwarder (custom patch)**
https://github.com/cparker15/connection-forwarder/tree/patch-1
* This Chrome App lets you expose Crostini / Android ports to LAN, so you can connect to servers running in Crostini from other devices. This can also be done on boot, unlike the built-in functionality within ChromeOS.
* The linked repository is a patched version which fixes the annoying permanent-crashing of the app. You have to build it yourself or you can install the .crx I packaged for myself [here](https://github.com/Granshmeyr/chronos/raw/main/extensions/connection-forwarder.crx).

Assuming your server is configured correctly, simply create a new rule in Connection Forwarder to expose the port:

> TCP 192.168.50.202:8080 (mlan0) → 100.115.92.195:8080

So, when I navigate to 192.168.50.202:8080 on my phone, it will connect to my server in Crostini which is bound to 100.115.92.195 of the eth0 device (visible with `ip a`). For a real example, I installed qbittorrent-nox and simply set the IP and Port in the Web UI settings. The ports you choose don't have to match and don't matter, but some might be reserved so just try anything.
