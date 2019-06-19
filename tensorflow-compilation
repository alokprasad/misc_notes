Tensor Flow Compilation

##########################################################################################
# Native Compilation of TensorFlow on Aarch64( PX2)
##########################################################################################
```
sudo apt-get install openjdk-8-jdk
sudo apt-get install pkg-config zip g++ zlib1g-dev unzip
wget https://github.com/bazelbuild/bazel/releases/download/0.21.0/bazel-0.21.0-dist.zip
unzip 
./compile.sh
sudo cp output/bazel /usr/local/bin

git clone https://github.com/tensorflow/tensorflow.git
cd tensorflow
git checkout r1.13
./configure ( i used CPU version)

Edit
https://github.com/tensorflow/serving/issues/832 --> in NVIDIA PX2
/home/nvidia/.cache/bazel/_bazel_nvidia/8f26d7d6518fcaa68e134c9b392fede3/external/aws/BUILD.bazel

bazel build -c opt --jobs=2 --verbose_failures  --copt="-funsafe-math-optimizations" \
--copt="-O3" --copt="-ftree-vectorize" --copt="-fomit-frame-pointer" //tensorflow:libtensorflow_cc.so


Note:
Add swap for OOM/Abort errors
sudo fallocate -l 4G /swapfile
sudo chmod 600 /swapfile
sudo mkswap /swapfile
sudo swapon /swapfile



