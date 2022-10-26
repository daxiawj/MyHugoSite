---
title: Mavericks apache2 issue after Server 3 removed
tags:
  - OSX
  - Apache
  - Server
  - 系统
date: 2014-03-28 11:26:15
category: 系统
---

After remove Server.app, my apache2 on Mac OS X 10.9.2 Mavericks couldn’t start normally while everything looks OK. After carefully studied the log file through Console.app and looked into the content of /usr/sbin/apachectl, I realized that the starting process of apache in OS X is quite different than that in Linux: it uses launchctl! 

So, I searched the apache launchctl config file:`/System/Library/LaunchDaemons/org.apache.httpd.plist`. Aha! it said: 

```xml
        <key>SERVER_INSTALL_PATH_PREFIX</key>
        <string>/Applications/Server.app/Contents/ServerRoot</string>
        ......
        and
    <key>ProgramArguments</key>
    <array>
        <string>/usr/sbin/httpd</string>
        <string>-D</string>
        <string>FOREGROUND</string>
        <string>-f</string>
        <string>/Library/Server/Web/Config/apache2/httpd_server_app.conf</string>
    </array>
```

The key `SERVER_INSTALL_PATH_PREFIX` and `ProgramArguments` were modified by Server.app aparently. Just recover them to `/usr` and `/etc/apache2/http.conf`, there, it works again!