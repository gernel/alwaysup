# alwaysup script to always check if service stop then re-start.

#!/bin/bash
service=httpd

if (( $(ps -ef | grep -v grep | grep $service | wc -l) > 0 ))
then
echo "$service is running!!!"
else
systemctl start $service
fi
