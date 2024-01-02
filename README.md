# Ubuntu-guide-after-initialize
---
# 0. apt
'''python
$ sudo apt update
$ sudo apt install net-tools
$ sudo apt install build-essential
'''
# 1. drivers
## 1. network
(especially there's no option for wired connection setting due to no ethernet driver)
1) $ lspci | grep -i Ethernet (check your ethernet driver version)
2) $ lshw -class network (if -network UNCLAIMED, there’ no driver)
3) go to realteck downloads(Realtek PCle) and download 2.5G/5G Ethernet LINUX driver
   (https://www.realtek.com/en/downloads) for general
   (https://www.realtek.com/en/directly-download?downloadid=73865466490b208c00b7ea79734b7ac4) for 240101
5) follow the instructions included on README
   {based on 240101}
   1} $ cd Downloads
   2} $ tar vjxf r8125-9.012.04.tar.bz2
   3} $ cd r8125-9.012.04
   4} $ sudo ./autorun.sh
