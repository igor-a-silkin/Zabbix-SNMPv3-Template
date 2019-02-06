# Zabbix-SNMPv3-Template
Zabbix template for LLD SNMPv3 Cisco network devices (switches and routers) with authentication and AES/DES encryption.


Template use next macros:

{$SNMP_V3_CONTEXTNAME} - context name.

{$SNMP_V3_SECURITYNAME} - security name.

{$SNMP_V3_AUTHPASSPHRASE} - authentication password.

{$SNMP_V3_PRIVPASSPHRASE} - private password.


Template has two version: for AES and DES encryption. There is localization Russian version for both too. 

Template use SHA authentication method. SNMP port is default.

Template tested in Zabbix 3.4 and 4.0. 

It work with next Cisco switches on AES encryption:
- 2960
- 2960G
- 2960X
- 3550
- 3750G

It work with next Cisco switches on DES encryption:
- 2950
- 2950G

It work with next Cisco routers on AES encryption:
- 2811

Template content:
- 4 element items:
 * temperature
 * CPU average load (5 min)
 * free memory
 * and some data from extrenal check by BASH-script:
  - IOS version
  - IOS flash file name
  - uptime
  - cooler status
  - temperature status
  - description of interface
  - admin status of interface
  - operational status of interface
  - VLAN/trunk of interface
   
- 3 triggers:
 * CPU high load of network item
 * Memory high load of network item
 * Temperature very high of network item
 
- 1 graphic:
 * CPU and memory average load
 
- 1 discovery rule for:
 * 8 element items prototypes
  -- Admin status of interface
  -- Alias of interface
  -- Description of interface
  -- Inbound errors on interface
  -- Incoming traffic on interafce
  -- Operational status of interface
  -- Outbound errors on interface
  -- Outgoing traffic on interface
  
 * 2 triggers prototypes
  -- Inbound errors host on interface
  -- Outbound errors host on interface
  
 * 1 graphic prototype:
  -- Traffic of interface
