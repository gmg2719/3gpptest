# 3gpptest
Quick hack to perform automated testing of IPv6 capabilities in 3GPP mobile networks when roaming.

The script will cycle through each available PLMN in each radio access technology and attempts to connect dual-stack, IPv6-only, and IPv4-only data bearers in each. If the connection is successful, it performs a couple of basic connectivity tests to verify that the network connection actually works.

It requires NetworkManager and ModemManager to actually establish the data bearers. Direct AT commands are used to set radio access technology and scan for and register in available PLMNs. It uses at least one Huawei proprietary AT command (`AT^SYSCFGEX`, used to set radio access technology), so it does probably not work with modems from other manufacturers.
