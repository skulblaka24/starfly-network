Network
=======

Pour debian, configure:
<pre><code>- eth0 en hotplug
- eth1 avec une ip
- wlan0 avec une ip 
</code></pre>

Pour RHEL:
<pre><code>- ifcfg-eth0
- ifcfg-eth1
</code></pre>

Attention à bien avoir les cartes reseaux qui correspondent.

Dans wlan0.j2:
 <pre><code>\- Si l'on ne commente pas gateway, on a l'erreur "RTNETLINK answers: File exists"
\- Failed to bring up wlan0." qui apparait dû à un duplicata avec eth0.
</code></pre>

Attention le wifi des rpi 3 ne prennent pas en charge le wifi de la freebox avec wpa2.

Requirements
------------

Ajouter une ip dans default avant de lancer le role.

Platform
--------

Debian ou RHEL

Role Variables
--------------

<pre><code>network_interface_to_be_changed: "ens33" # ens33 (Virtual) ou enp0f1 (Physical)

network_enable_eth0: "yes"
network_enable_eth1: "no"
network_enable_wlan0: "no"

network_eth1_ip: 172.167.54.34
network_eth1_netmask: 255.255.255.0
network_eth1_gateway: "" # Ou vide

network_wlan0_ip: 192.168.23.34
network_wlan0_netmask: 255.255.255.0
network_wlan0_gateway: "" # gateway 192.168.1.254 Ou vide

network_wifi_ssid: "Toad's Kingdom"
network_wifi_password: "54718e8e6a5314e7e91167227038e0d07ffcf8890dde556db14fd34d6e394249"
</code></pre>

Dependencies
------------

Ce role se télécharge automatiquement à partir du requirements.yml


Author Information
------------------

Starfly Env Team
