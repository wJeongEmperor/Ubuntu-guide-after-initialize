# Ubuntu-guide-after-initialize
basic guide line under setup ubuntu for me from the near future after initialization :)
---
# 0. apts
```
sudo apt update
sudo apt install net-tools
sudo apt install build-essential
sudo apt git
conda update -n base -c defaults conda
```
* unzip command
```python
tar -xvf "~.tar"
tar -zxvf "~.tar.gz"
unzip "~.zip"
```
# 1. drivers
## 1. network
(especially there's no option for wired connection setting due to no ethernet driver)
```python
lspci | grep -i Ethernet #check your ethernet driver version
lshw -class network #if -network UNCLAIMED, there’ no driver
#go to realteck downloads(Realtek PCle) and download 2.5G/5G Ethernet LINUX driver
#   (https://www.realtek.com/en/downloads) for general
#   (https://www.realtek.com/en/directly-download?downloadid=73865466490b208c00b7ea79734b7ac4) for 240101
#follow the instructions included on README{based on 240101}
cd Downloads
tar vjxf r8125-9.012.04.tar.bz2
cd r8125-9.012.04
sudo ./autorun.sh
```
## 2. hangul keyboard
[ref](https://driz2le.tistory.com/253)
```python
sudo apt-get install fcitx-hangul
#Setting->Region&Language->Manage Installed Languages
#Keyboard input method system:fcitx
#restart
#Top of the right(keyboard)->Configure->(tap)Input Method(+)->(unchecked)Only Show Current Language->(put)hangul
#(tap)Global Config->Trigger Input Method(what you want to make a button)
```
# 2. programs
## 0. etc
```python
sudo snap install glances #cpu,memory,gpu monitor
sudo snap install teams-for-linux #teams
pip install gpustat #gpustat -i
```
## 1. VS code
[download](https://code.visualstudio.com/)
```python
#download .deb
sudo apt install ./"filename"
code #run vs code
```
## 2. Anaconda
[download](https://www.anaconda.com/download)
[ref](https://ieworld.tistory.com/12)
```python
bash "setup filename"
sudo gedit ~/.bashrc
#text editor//add below endline//
export PATH=~/anaconda3/bin:~/anaconda3/condabin:$PATH
#end
source ~/.bashrc
conda config --set auto_activate_base False
```
all of setup-action should be recomended under virtual environment.</br>
* linkage with vscode
```python
#open vscode and install extentions python and code runner
#restart vscode
#ctrl+shift+p>python:select interpreter
#ctrl+` #open terminal
```
## 3. Isaacgym
[download](https://developer.nvidia.com/isaac-gym/download)
## 4. CUDA
[download](https://developer.nvidia.com/cuda-toolkit-archive)
[ref](https://webnautes.tistory.com/1844)</br>
Notice : Using virtual environment is highly recommended before install CUDA and cuDNN as well as others.
</br>
direct download using conda
```python
#download CUDA toolkit ver11.8
conda install -c anaconda cudatoolkit
```
also cuDNN can be installed by using conda
```python
conda install -c anaconda cudnn
```
# 3. Codes
## 1. ASE
last updated on 240102</br>
1. [Isaacgym download](https://developer.nvidia.com/isaac-gym/download)
2. [ASE](https://github.com/nv-tlabs/ASE.git)
# 4. Virtual environment(Anaconda)
```python
<command list>
python --version
conda create -n "virtual env. name" python=3.8
conda env list #check environment list
conda activate "env. name"
conda deactivate
pip install "package name"
pip list #check package list
pip freeze > requirements.txt #save all package on list
pip install -r requirements.txt #install all package on the list
pip install --upgrade "name"<="version" #install package specified version
nvidia-smi #chech nvidia version
```
# 5. Learning issues
* RuntimeError: CUDA out of memory.</br>
  lower batch size, #environment
# 6. Hotkeys
* screenshot : shift+PrtSc
* screencapture : ctrl+alt+shift+r
