--------------------
Preparing the System
--------------------

Hostname
========

If the hostname was not set during **First Boot** you can modify ``/etc/sysconfig/network``.

::

    # /etc/sysconfig/network
    NETWORKING=yes
    HOSTNAME=invttmtjwx03.tmtj.invite-comm.jp

Client Routing
==============

Create a routing file in ``/etc/sysconfig/network-scripts`` for client facing interfaces.  For example ``eth2`` would use ``/etc/sysconfig/network-scripts/route-eth2`` to route to the client network.

::

    # /etc/sysconfig/network-scripts/route-eth2
    192.168.0.0/24 via 172.16.0.10
    10.0.0.0/24 via 172.16.0.10
    

.. tip::
    This is the **best** point to run ``sys-unconfig`` and create the **clone** of the virtual machine.  Additional settings are *specific** the each virtual machine.
    
Prepare the Asterisk Template
=============================

Find a suitable template.
-------------------------

Find an MCAT configuration that performs a role similar to the new MCAT server.

============ =================
invttmtjtest Example Template
invttmtjwx03 Sample Server
invttmtjwx04 Sample Clone
============ =================

::

    cd /home/mcat
    svn cp invttmtjtest invttmtjwx03
    svn commit -m "Base Config invttmtjwx03" invttmtjwx03
    




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


