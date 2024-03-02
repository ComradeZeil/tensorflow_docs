# Install TensorFlow using Windows Subsystem for Linux 2 (WSL 2)

Refer to [TensorFlow](https://www.tensorflow.org/install/pip#windows-wsl2) website for more information.

1. Enable WSL 2 by typing `D:\tensorflow-docs> wsl` in command prompt. 
2. Switch to Python virtual environment. (If no venv create one first. )
3. In WSL interface, install cuda toolkit (Make sure you have NVIDIA GPU driver installed before!!)
   ```
    $ wget https://developer.download.nvidia.com/compute/cuda/repos/wsl-ubuntu/x86_64/cuda-keyring_1.1-1_all.deb
    $ sudo dpkg -i cuda-keyring_1.1-1_all.deb
    $ sudo apt-get update
    $ sudo apt-get -y install cuda-toolkit-12-3
   ```
4. Install TensorFlow in this step by typing: 
   ```
   $ python3 -m pip install tensorflow[and-cuda]
   ```
   This step will take a while. 
5. To verify GPU setup:
   ```
   $ python3 -c "import tensorflow as tf; print(tf.config.list_physical_devices('GPU'))"
   ```
   Verify CPU setup:
   ```
   $ python -c "import tensorflow as tf; print(tf.reduce_sum(tf.random.normal([1000, 1000])))"
   ```