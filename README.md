# Ubuntu-guide-after-initialize
base guide line for setup ubuntu after initialization
---
# 0. apts
```
sudo apt update
sudo apt install net-tools
sudo apt install build-essential
```
# 1. drivers
## 1. network
(especially there's no option for wired connection setting due to no ethernet driver)
```python
lspci | grep -i Ethernet //check your ethernet driver version
lshw -class network //if -network UNCLAIMED, there’ no driver
//go to realteck downloads(Realtek PCle) and download 2.5G/5G Ethernet LINUX driver
//   (https://www.realtek.com/en/downloads) for general
//   (https://www.realtek.com/en/directly-download?downloadid=73865466490b208c00b7ea79734b7ac4) for 240101
//follow the instructions included on README{based on 240101}
cd Downloads
tar vjxf r8125-9.012.04.tar.bz2
cd r8125-9.012.04
sudo ./autorun.sh
```
## 2. hangul keyboard
(ref) https://driz2le.tistory.com/253
```python
sudo apt-get install fcitx-hangul
//Setting->Region&Language->Manage Installed Languages
//Keyboard input method system:fcitx
//restart
//Top of the right(keyboard)->Configure->(tap)Input Method(+)->(unchecked)Only Show Current Language->(put)hangul
//(tap)Global Config->Trigger Input Method(what you want to make a button)
```
# 2. programs
## 1. VS code
[download](https://code.visualstudio.com/)
```python
//download .deb
sudo apt install ./"filename"
code //run vs code
```
## 2. Anaconda
[download](https://www.anaconda.com/download)
```python
bash "setup filename"
sudo gedit ~/.bashrc
//text editor//add below endline//
export PATH=~/anaconda3/bin:~/anaconda3/condabin:$PATH
//
source ~/.bashrc
conda config --set auto_activate_base False
```
