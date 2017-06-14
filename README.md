
ubuntu/images/hvm-ssd/ubuntu-xenial-16.04-amd64-server-20170414 (ami-efd0428f)

sudo -i
nvcc --version
apt-get update && apt-get upgrade

wget http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1404/x86_64/cuda-repo-ubuntu1404_8.0.61-1_amd64.deb
sudo dpkg -i cuda-repo-ubuntu1404_8.0.61-1_amd64.deb
sudo apt-get update
sudo apt-get install cuda

`sudo apt-get install nvidia-cuda-toolkit`

sudo apt-get install libprotobuf-dev libleveldb-dev libsnappy-dev \
libopencv-dev libhdf5-serial-dev protobuf-compiler -y \
&& sudo apt-get install --no-install-recommends libboost-all-dev -y \
&& sudo apt-get install libatlas-base-dev -y \
&& sudo apt-get install libgflags-dev libgoogle-glog-dev liblmdb-dev -y

https://developer.nvidia.com/compute/machine-learning/cudnn/secure/v6/prod/8.0_20170427/Ubuntu16_04_x64/libcudnn6_6.0.21-1+cuda8.0_amd64-deb
https://developer.nvidia.com/compute/machine-learning/cudnn/secure/v6/prod/8.0_20170427/Ubuntu16_04_x64/libcudnn6-dev_6.0.21-1+cuda8.0_amd64-deb

sudo dpkg -i libcudnn6*.deb
sudo apt-get update
sudo apt-get install libcudnn6

sudo dpkg -i libcudnn6-dev*.deb
sudo apt-get update
sudo apt-get install libcudnn6-dev

sudo apt-get install libopencv-dev -y
sudo apt-get install libopenblas-dev -y
sudo apt-get install libatlas-base-dev -y
sudo apt-get install python-numpy -y

https://devtalk.nvidia.com/default/topic/617414/-solved-cuda-driver-version-is-insufficient-for-cuda-runtime-version-fedora-18-rpmfusion-driver/
cd /usr/lib[64]/nvidia
sudo ln -s libcuda.so.1 libcuda.so
sudo ldconfig

https://github.com/BVLC/caffe/issues/1284#issuecomment-59381509

sudo apt-get install git -y \
&& git clone https://github.com/CMU-Perceptual-Computing-Lab/openpose.git \
&& cd openpose \
&& cp Makefile.config.Ubuntu16.example Makefile.config \
&& chmod u+x install_caffe_and_openpose.sh \
&& ./install_caffe_and_openpose.sh


./build/examples/openpose/openpose.bin --num_gpu 1 --image_dir examples/media/ \
--write_images examples/media/output --write_keypoint_json examples/media/output


================================================================================

sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    software-properties-common

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"

sudo apt-get update

sudo apt-get install docker-ce



https://github.com/NVIDIA/nvidia-docker/wiki/Installation#installing-from-binary-packages
