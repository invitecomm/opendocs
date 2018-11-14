##################
Prepare the System
##################

========
Hostname
========

If the hostname was not set during **First Boot** you can modify ``/etc/sysconfig/network``.

::

    # /etc/sysconfig/network
    NETWORKING=yes
    HOSTNAME=invttmtjwx03.tmtj.invite-comm.jp

==============
Client Routing
==============

Create a routing file in ``/etc/sysconfig/network-scripts`` for client facing interfaces.  For example ``eth2`` would use ``/etc/sysconfig/network-scripts/route-eth2`` to route to the client network.

::

    # /etc/sysconfig/network-scripts/route-eth2
    192.168.0.0/24 via 172.16.0.10
    10.0.0.0/24 via 172.16.0.10
    

cd /home/mcat
svn cp _ORI_ _NEW_
svn commit -m "Base Config _NEW_" _NEW_
cd /etc
rm asterisk
ln -s /home/mcat/d863906085/etc/asterisk asterisk

vi sip.conf
--- [their host]
username=this host 
host=192.168.32.26 there ip
accountcode=INVTTMTJSL02-MCAT
[mcat](!)
accountcode=MCAT-INVTTMTJSL02
---
vi extensions.conf
---
[INBOUND]
exten => _X.,n,Dial(SIP/__SDIVGMOCL002__/${EXTEN})
---


