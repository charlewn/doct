# Install cuda 8 and cdnn 6 on ubuntu 16.04

https://developer.nvidia.com/cuda-80-ga2-download-archive

sudo dpkg -i cuda-repo-ubuntu1404-8-0-local-ga2_8.0.61-1_amd64-deb

sudo apt-get update

sudo apt-get install cuda

sudo apt-get install cuda-toolkit-driver

sudo apt purge nvidia-*
sudo add-apt-repository ppa:graphics-drivers/ppa
sudo apt update
sudo apt install nvidia-384


## add in .bashrc
export PATH=/usr/local/cuda-8.0/bin${PATH:+:${PATH}}

export LD_LIBRARY_PATH=/usr/local/cuda-8.0/lib64${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}


nvcc -V

nvidia-smi

## install cuDNN v6.0
CUDNN_TAR_FILE="cudnn-8.0-linux-x64-v6.0.tgz"

wget http://developer.download.nvidia.com/compute/redist/cudnn/v6.0/${CUDNN_TAR_FILE}

tar -xzvf ${CUDNN_TAR_FILE}

sudo cp -P cuda/include/cudnn.h /usr/local/cuda-8.0/include

sudo cp -P cuda/lib64/libcudnn* /usr/local/cuda-8.0/lib64/

sudo chmod a+r /usr/local/cuda-8.0/lib64/libcudnn*

# To remove
sudo apt-get --purge remove cuda
sudo apt autoremove
