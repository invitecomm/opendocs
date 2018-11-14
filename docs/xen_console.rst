##########
First Boot
##########



.. image:: images/mcat/xen_console_001.png
    :scale: 25 %
    
Root Password
-------------

When the newly created VM is booted for the first time, you'll be prompted to enter change the ``root`` password.  

.. important:: 
    Use the standard INVITE password for the root account.
    
.. image:: images/mcat/xen_console_002.png
    :scale: 50 %
    
.. image:: images/mcat/xen_console_003.png
    :scale: 50 %
    
.. image:: images/mcat/xen_console_004.png
    :scale: 50 %

Device Configuration
--------------------

====== =========== ============= === ==================
Subnet Network     Network Mask  Bit Purpose
====== =========== ============= === ==================
OAM&P  172.24.12.0 255.255.252.0 /22 Management Network
MCAT   172.17.70.0 255.255.255.0 /24 Core MCAT Network
Client d.d.d.d     d.d.d.d       \   Client Connections
====== =========== ============= === ==================

IP addressing follows a common host number convention.  Where all the IP addresses **end** with the same digit.  When the client *specified* subnet allows. 

The host number **must** be used for all the internal subnets used on the MCAT platform.::

    # Common Host Number = 254
    OAM&P = 172.24.15.254
    MCAT = 172.17.70.254
    Client = 192.168.0.254

.. warning::
    **Only** the OAM&P network (``eth0``) *should* have the ``Default gateway IP`` **and** ``DNS server`` settings.  Leave these settings **empty** for **other** network interfaces.
    
.. important::
    *Some* carriers *require* the network interface is the **primary** connection.  This **requires** a *different* connectivity model to be used.

.. image:: images/mcat/xen_console_005.png
    :scale: 50 %
    
.. image:: images/mcat/xen_console_006.png
    :scale: 50 %
    
.. image:: images/mcat/xen_console_007.png
    :scale: 50 %
    
.. image:: images/mcat/xen_console_008.png
    :scale: 50 %
    
.. image:: images/mcat/xen_console_009.png
    :scale: 50 %

.. image:: images/mcat/xen_console_010.png
    :scale: 50 %
    
.. image:: images/mcat/xen_console_011.png
    :scale: 50 %
    
.. image:: images/mcat/xen_console_012.png
    :scale: 50 %
    
.. image:: images/mcat/xen_console_013.png
    :scale: 50 %
    
.. image:: images/mcat/xen_console_014.png
    :scale: 50 %
    
.. image:: images/mcat/xen_console_015.png
    :scale: 50 %
    
.. image:: images/mcat/xen_console_016.png
    :scale: 50 %
    
.. image:: images/mcat/xen_console_017.png
    :scale: 50 %
    
.. image:: images/mcat/xen_console_018.png
    :scale: 50 %
    
.. image:: images/mcat/xen_console_019.png
    :scale: 50 %

.. image:: images/mcat/xen_console_020.png
    :scale: 50 %
    
.. image:: images/mcat/xen_console_021.png
    :scale: 50 %
    
DNS configuration
-------------------------

.. hint:: 
    The hostname can be set at this stage in the process -or- by directly editing ``/etc/sysconfig/network``.  Changing the hostname directly **requires** the VM to be rebooted *again*.

::

    # /etc/sysconfig/network    
    NETWORKING=yes
    HOSTNAME=wx03.tmtj.invite-comm.jp  

.. image:: images/mcat/xen_console_022.png
    :scale: 50 %  

.. image:: images/mcat/xen_console_023.png
    :scale: 50 %
    
.. image:: images/mcat/xen_console_024.png
    :scale: 50 %
    
.. image:: images/mcat/xen_console_025.png
    :scale: 50 %

.. image:: images/mcat/xen_console_026.png
    :scale: 50 %
    
.. image:: images/mcat/xen_console_027.png
    :scale: 50 %
    
.. image:: images/mcat/xen_console_028.png
    :scale: 50 %
    
.. image:: images/mcat/xen_console_029.png
    :scale: 50 %

.. image:: images/mcat/xen_console_030.png
    :scale: 50 %
    
.. image:: images/mcat/xen_console_031.png
    :scale: 50 %
