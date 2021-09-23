# Gebruik VM

Ik raad aan om vncviewer over ssh te gebruiken. Blijkbaar heeft de huidige image by default geen encryptie, dus kan je dit bereiken over een ssh tunnel. Je kan de poort 5900 publiek openzetten, waardoor je er van buitenaf zal aankunnen. Bijvoorbeeld:

* Poort 10009 = ssh access
* Poort 10010 = port forward naar je machine poort 5900. LET OP: je moet wel op je vncserver publieke connecties toelaten, zoniet kan je er enkel via ssh & localhost op.

Hier gaan we overlopen hoe je de ssh tunnel met Putty kan configureren.

## SSH tunnel

### Basis configuratie + ssh tunnel

![Base config](./pics/01-putty-base-config.png)
![SSH tunnel config](./pics/02-ssh-tunnel-config.png)

### Inloggen

Dit is vanzelfsprekend, maar vanaf je op "Open" drukt kan je inloggen als user `user`.

![SSH login](./pics/03-ssh-login.png)

**Het kan zijn dat je oftewel je local port forward moet aanpassen, of je vnc server port. Kijk hiervoor onderaan bij "Extra: VNC server poort wijzigen".**

## VNC Viewer config

![New connection](./pics/04-vncviewer-new-connection.png)
![Config](./pics/05-vncviewer-config.png)

**LET OP: stel je vnc password in met `vncpasswd`.**

![Authenticate](./pics/06-vncviewer-authenticate.png)
![Preview](./pics/07-vncviewer-preview.png)

Veel plezier!

## Extra: VNC server poort wijzigen

### Sessies oplijsten

![List vncserver sessions](./pics/08-view-vncserver-port.png)

### Poort wijzigen & sessie afsluiten

Op onderstaande afbeelding kan je zien hoe je een nieuwe vnc server sessie maakt, waarna je alles oplijst. Dan kill je de (onnodige) sessie, waarna je het nakijkt met `vncserver -list`

![Change port with rfbport option](./pics/09-instructions-rfbport.png)

Je kan ook je dimensies etc... configureren. Lees `vncserver --help`.
