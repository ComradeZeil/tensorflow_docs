# Install TensorFlow using Windows Subsystem for Linux 2 (WSL 2)

Generally, it is recommended that you install WSL 2-supported TensorFlow on Windows 11, since WSL 2 works better on the latest Windows OS. Refer to [TensorFlow](https://www.tensorflow.org/install/pip#windows-wsl2) website for more information. [This](/Install_TensorFlow_WSL2.md#install-wsl-2-on-windows) section instructs how to install WSL 2 on Windows 10 and 11. 

1. Enable WSL 2 by typing `$WorkFolder> wsl` in command prompt. 
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

## Install WSL 2 on Windows

*WSL 2 works best with Windows 11, not only it enables Linux GUI applications, but also it better supports the Linux-orientated packages. It is not recommended to install TensorFlow on Windows 10 WSL 2 because there are dependencies issues with respect to CUDA Toolkit. There is also a bad support on Numpy long double data type.* 

1. Open command prompt or Powershell. Type `> wsl --install -d Ubuntu`. 
2. Wait for WSL-Ubuntu system to finish installation. 
3. After installation, a second window will pop up and prompt for username and password. 
4. Once created a local profile on the WSL environment, restart the machine. 
5. Open WSL environment. Have fun playing with Linux system on Windows! 
