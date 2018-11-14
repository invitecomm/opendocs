##########
First Boot
##########



.. image:: images/mcat/xen_console_001.png
    :scale: 25 %

=============    
Root Password
=============

When the newly created VM is booted for the first time, you'll be prompted to enter change the ``root`` password.

* 該当のサーバをつかまえて、コンソールをみる

.. important:: 
    Use the standard INVITE password for the root account.
    
.. image:: images/mcat/xen_console_002.png
    :scale: 50 %
    
.. image:: images/mcat/xen_console_003.png
    :scale: 50 %
    
.. image:: images/mcat/xen_console_004.png
    :scale: 50 %

====================
Device Configuration
====================

====== =========== ============= === ==================
Subnet Network     Network Mask  Bit Purpose
====== =========== ============= === ==================
OAM&P  172.24.12.0 255.255.252.0 /22 Management Network
MCAT   172.17.70.0 255.255.255.0 /24 Core MCAT Network
Client d.d.d.d     d.d.d.d       \   Client Connections
====== =========== ============= === ==================

IP addressing follows a common host number convention.  Where all the IP addresses **end** with the same digit.  ``___.___.___.254``  Where a client *specified* subnet allows.  The host number **must** be used for all the internal subnets used on the MCAT platform.::

    # Default Host Number = 254
    OAM&P = 172.24.15.254
    MCAT = 172.17.70.254
    Client = 192.168.0.254


.. warning::
    **Only** the OAM&P network (``eth0``) *should* have the ``Default gateway IP`` **and** ``DNS server`` settings.  Leave these settings **empty** for **other** network interfaces.
    
.. important::
    *Some* carriers *require* the network interface is the **primary** connection.  This **requires** a *different* connectivity model to be used.

.. image:: images/mcat/xen_console_005.png
    :scale: 50 %
    
OAM&P ``eth0``
--------------
    
.. image:: images/mcat/xen_console_006.png
    :scale: 50 %
    
.. image:: images/mcat/xen_console_007.png
    :scale: 50 %
    
.. image:: images/mcat/xen_console_008.png
    :scale: 50 %
    
Change the ``Static IP`` to use the correct host number.
    
.. image:: images/mcat/xen_console_009.png
    :scale: 50 %

.. image:: images/mcat/xen_console_010.png
    :scale: 50 %
    
    
MCAT ``eth1``
--------------

.. image:: images/mcat/xen_console_011.png
    :scale: 50 %
    
.. image:: images/mcat/xen_console_012.png
    :scale: 50 %
    
.. image:: images/mcat/xen_console_013.png
    :scale: 50 %
    
Change the ``Static IP`` to use the correct host number.

    
.. image:: images/mcat/xen_console_014.png
    :scale: 50 %
    
.. image:: images/mcat/xen_console_015.png
    :scale: 50 %
    
Adding Network Interfaces
-------------------------

For *each* additional network interface needed to support the client, perform the following steps.
    
* Select ``New Device``.

.. image:: images/mcat/xen_console_016.png
    :scale: 50 %

* Choose ``Ethernet`` as the device type.

.. image:: images/mcat/xen_console_017.png
    :scale: 50 %
    
* Select ``Add``.
    
.. image:: images/mcat/xen_console_018.png
    :scale: 50 %
    
* Enter the ``Network Configuration`` details.
    
.. image:: images/mcat/xen_console_019.png
    :scale: 50 %
    
The ``Name`` and ``Device`` **should** increment from the last configured interface.  ``eth2``, ``eth3``, ``eth4``, etc...

.. warning::
    **Only** the OAM&P network (``eth0``) *should* have the ``Default gateway IP`` **and** ``DNS server`` settings.  Leave these settings **empty** for **other** network interfaces.

.. image:: images/mcat/xen_console_020.png
    :scale: 50 %
    
* Select ``Save`` once all the devices have been configured.
    
.. image:: images/mcat/xen_console_021.png
    :scale: 50 %
    
=================
DNS configuration
=================

The hostname *may* be the long INVITE CLLI styled ID or the short version.
::

    invttmtjwx03.tmtj.invite-comm.jp
    -or-
    wx03.tmtj.invite-comm.jp


.. hint:: 
    The hostname can be set at this stage in the process -or- by directly editing ``/etc/sysconfig/network``.  Changing the hostname directly **requires** the VM to be rebooted *again*.

::

    # /etc/sysconfig/network    
    NETWORKING=yes
    HOSTNAME=wx03.tmtj.invite-comm.jp  

.. image:: images/mcat/xen_console_022.png
    :scale: 50 %  

* Enter the ``DNS Configuration`` details.

===================  ======================================
Field                Setting
===================  ======================================
``Hostname``         *hostname* ``.tmtj.invite-comm.jp``
``Primary DNS``      ``172.24.15.51`` *internal*
``Secondary DNS``    ``172.24.15.52`` *internal*
``Tertiary DNS``     ``8.8.8.8`` *external for backup*
``DNS search path``  ``tmtj.invite-comm.jp invite-comm.jp``
===================  ======================================


.. image:: images/mcat/xen_console_023.png
    :scale: 50 %
    
.. image:: images/mcat/xen_console_024.png
    :scale: 50 %

* Select ``OK``

.. image:: images/mcat/xen_console_025.png
    :scale: 50 %

.. image:: images/mcat/xen_console_026.png
    :scale: 50 %
    
* Select ``Save&Quit``
    
.. image:: images/mcat/xen_console_027.png
    :scale: 50 %

============================
Authentication Configuration
============================

The first boot process with *prompt* for ``Authentication Configuration`` settings.  *This may be skipped.*

.. image:: images/mcat/xen_console_028.png
    :scale: 50 %
    
* Select ``Next`` and the system **will reboot**
    
.. image:: images/mcat/xen_console_029.png
    :scale: 50 %


.. image:: images/mcat/xen_console_030.png
    :scale: 50 %
    
.. image:: images/mcat/xen_console_031.png
    :scale: 50 %

* Done

.. attention::

    You can now connect to the system *via* ``ssh``.
