---
id: 7lubovdrv3f48dmk97jsbxm
title: Ssh
desc: ''
updated: 1723636850023
created: 1723636850023
isDir: false
---
rsync --append -azv -e 'ssh -o "ProxyCommand ssh -A $JUMPHOST -W %h:%p"' $1 $USER@$DEVBOX:/home/$USER/$2



PGPASSWORD="temp4fu!" psql -h 127.0.0.1 -p 5432 -U dbAdmin -f $1 heimdall