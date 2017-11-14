# Install cuda 8 and cdnn 6 on ubuntu 16.04

https://developer.nvidia.com/cuda-80-ga2-download-archive

$ sudo dpkg -i cuda-repo-ubuntu1404-8-0-local-ga2_8.0.61-1_amd64-deb
$ sudo apt-get update
$ sudo apt-get install cuda

sudo apt-get install cuda-toolkit-driver

sudo apt purge nvidia-*
sudo add-apt-repository ppa:graphics-drivers/ppa
sudo apt update
sudo apt install nvidia-384

nvcc -V

nvidia-smi

# To remove
sudo apt-get --purge remove cuda
sudo apt autoremove
