# Install TensorFlow using Windows Subsystem for Linux 2 (WSL 2)

1. Enable WSL 2 by typing `D:\tensorflow-docs> wsl` in command prompt. 
2. In WSL interface, install cuda toolkit (Make sure you have NVIDIA GPU driver installed before!!)
   ```
    $ wget https://developer.download.nvidia.com/compute/cuda/repos/wsl-ubuntu/x86_64/cuda-keyring_1.1-1_all.deb
    $ sudo dpkg -i cuda-keyring_1.1-1_all.deb
    $ sudo apt-get update
    $ sudo apt-get -y install cuda-toolkit-12-3
   ```
3. Install TensorFlow in this step by typing: 
   ```
   $ python3 -m pip install tensorflow[and-cuda]
   ```
   This step will take a while. 
4. To verify the installation:
   ```
   $ python3 -c "import tensorflow as tf; print(tf.config.list_physical_devices('GPU'))"
   ```