# Install on Windows via PIP

## Environmental preparation

### 1.1 PREQUISITES

* **Windows 7/8/10 Pro/Enterprise (64bit)**
  * **GPU version support CUDA 9.0/9.1/9.2/10.0/10.1，only supports single card**
  
* **Python version 2.7.15+/3.5.1+/3.6/3.7/3.8 (64 bit)**

* **pip version 9.0.1+ (64 bit)**

### 1.2 How to check your environment

* You can use the following commands to view the local operating system and bit information

  ```
  uname -m && cat /ect/*release
  ```


* Confirm that the Python where you need to install PaddlePaddle is your expected location, because your computer may have multiple Python

  * If you are using Python 2, use the following command to output Python path. Depending on the environment, you may need to replace Python in all command lines in the description with specific Python path

    ```
    which python
    ```

  * If you are using Python 3, use the following command to output Python path. Depending on your environment, you may need to replace Python 3 in all command lines in the instructions with Python or specific Python path

    ```
    which python3
    ```

    

* You need to confirm whether the version of Python meets the requirements

  * If you are using Python 2, use the following command to confirm that it is 2.7.15+

        python --version

  * If you are using Python 3, use the following command to confirm that it is 3.5.1+/3.6/3.7/3.8

        python3 --version

* It is required to confirm whether the version of pip meets the requirements. The version of pip is required to be 9.0.1+

  * If you are using Python 2

    ```
    python -m ensurepip
    ```

    ``` 
    python -m pip --version
    ```

  * If you are using Python 3

    ```
    python3 -m ensurepip
    ```

    ``` 
    python3 -m pip --version
    ```

  

* You need to confirm that Python and pip are 64bit, and the processor architecture is x86_64(or called x64、Intel 64、AMD64). Currently, paddlepaddle does not support arm64 architecture. The first line below outputs "64bit", and the second line outputs "x86_64", "x64" or "AMD64"

  * If you are using Python 2

    ```
    python -c "import platform;print(platform.architecture()[0]);print(platform.machine())"
    ```

  * If you are using Python 3

    ```
    python3 -c "import platform;print(platform.architecture()[0]);print(platform.machine())"
    ```

    

* The installation package provided by default requires computer support for MKL

* If you do not know the machine environment, please download and use[Quick install script](https://fast-install.bj.bcebos.com/fast_install.sh), for instructions please refer to[here](https://github.com/PaddlePaddle/FluidDoc/tree/develop/doc/fluid/install/install_script.md)。



## INSTALLATION

If you installed Python via Homebrew or the Python website, `pip` was installed with it. If you installed Python 3.x, then you will be using the command `pip3`. We will introduce pip installation here.

### Choose CPU/GPU

* If your computer doesn't have NVIDIA® GPU, please install [the CPU Version of PaddlePaddle](#cpu)

* If your computer has NVIDIA® GPU, please make sure that the following conditions are met and install [the GPU Version of PaddlePaddle](#gpu)

  * **CUDA toolkit 9.0/10.0 with cuDNN v7.6+**

  * **Hardware devices with GPU computing power over 1.0**

    You can refer to NVIDIA official documents for installation process and configuration method of CUDA and cudnn. Please refer to [CUDA](https://docs.nvidia.com/cuda/cuda-installation-guide-linux/)，[cuDNN](https://docs.nvidia.com/deeplearning/sdk/cudnn-install/)



## Installation Step

You can choose the following version of PaddlePaddle to start installation:

* [CPU Version of PaddlePaddle](#cpu)

* [GPU Version of PaddlePaddle](#gpu)
  * [CUDA9.0 PaddlePaddle](#cuda9)
  * [CUDA10.0 PaddlePaddle](#cuda10)



#### 2.1 <span id="cpu">CPU Versoion of PaddlePaddle</span>

* If you are using Python 2

  ```
  python -m pip install paddlepaddle==1.8.5 -i https://mirror.baidu.com/pypi/simple
  ```

* If you are using Python 3

  ```
  python3 -m pip install paddlepaddle==1.8.5 -i https://mirror.baidu.com/pypi/simple
  ```

  

#### 2.2<span id="gpu"> GPU Version of PaddlePaddle</span>



2.2.1 <span id="cuda9">CUDA9.0 PaddlePaddle</span>

* If you are using Python 2

  ```
  python -m pip install paddlepaddle-gpu==1.8.5.post97 -f https://paddlepaddle.org.cn/whl/stable.html
  ```

* If you are using Python 3

  ```
  python3 -m pip install paddlepaddle-gpu==1.8.5.post97 -f https://paddlepaddle.org.cn/whl/stable.html
  ```

  

2.2.1 <span id="cuda10">CUDA10.0 PaddlePaddle</span>

* If you are using Python 2

  ```
  python -m pip install paddlepaddle-gpu==1.8.5.post107 -f https://paddlepaddle.org.cn/whl/stable.html
  ```

* If you are using Python 3

  ```
  python3 -m pip install paddlepaddle-gpu==1.8.5.post107 -f https://paddlepaddle.org.cn/whl/stable.html
  ```

  


## Verify installation

After the installation is complete, you can use `python` or `python3` to enter the Python interpreter and then use `import paddle.fluid` and `fluid.install_check.run_check()`

If `Your Paddle Fluid is installed succesfully!` appears, to verify that the installation was successful.

## How to uninstall

Please use the following command to uninstall PaddlePaddle:

* **CPU version of PaddlePaddle**: `python -m pip uninstall paddlepaddle`

* **GPU version of PaddlePaddle**: `python -m pip uninstall paddlepaddle-gpu`