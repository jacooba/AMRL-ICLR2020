# AMRL REAMDE

Modifications to RLLib used for the paper AMRL: Aggregated Memory For Reinforcement Learning published at ICLR 2020 (https://iclr.cc/virtual_2020/poster_Bkl7bREtDr.html).

# Installation:

install python 3.5 #e.g. conda create -n AMRL python=3.5  
pip install --upgrade pip #may not be necessary  
pip install requests  
sudo apt install ffmpeg  
sudo apt install gcc  
sudo apt install python3-dev  

>**Building ray-0.6.2 from source:**
>
>Note that this project was run with a private and altered version of ray-0.6.2. The files in this repo should provide all code needed for the AMRL experiments. Howerver, supporitng code in the rest of Rllib will likely needed to me changed for compataibilty, so these instructions may be incomplete. The following steps work for the modified version.
>
>First, diffs from this repo need to be applied to the appropriate files in ray-0.6.2. This will ensure that code relevant for the AMRL modifications is correct. For all files in this repo that that end in "_diff", the diff should first be applied to recover the correct code. Instructions on how to do this, and a link to the correct file to apply the diff to, should be at the top of each file.
>
>Second, the files in this repo (including those resulting from the applied diffs) need to be moved to the appropriate directories in ray-0.6.2. Specifically, the files in ./python scripts here should be moved to python/ray/rllib; files in ./models here should be moved into python/ray/rllib/models;  files in ./experiments here should be moved into python/ray/rllib/examples; files in ./bash_scripts should work from anywhere. 
>
>Next, move to the ray repo, and build ray from source using the instructions below.
>
>To do this, install bazel (e.g. from https://github.com/bazelbuild/bazel/releases/download/0.26.1/bazel-0.26.1-installer-${platform}-x86_64.sh). Make sure bazel command works, and add it to path if it does not.  
>
>Then run the remaining commands.

sudo apt update  
sudo apt install build-essential  
sudo apt install curl  
sudo apt install unzip  
sudo apt install psmisc  
sudo apt install cmake  
sudo apt install flex  
sudo apt install bison  

> Other likely required apt installs:  
> libboost-all-dev  
  libpython3.5-dev  
  openjdk-8-jdk  
  python3-pip  
  python3-setuptools  
  python3-tk  
  libav-tools  
  wget  
  libssl-dev  
  libffi-dev  
  python-dev  
  x11-xserver-utils  
  xvfb  
  libtiff5-dev  
  libjpeg8-dev  
  zlib1g-dev  
  libfreetype6-dev  
  liblcms2-dev  
  libwebp-dev  
  tcl8.5-dev  
  netcat  
  iputils-ping  
  net-tools  
  vim  
  tk8.5-dev

pip install cython==0.29.0 pytest #may not be necessary  
pip install pyarrow #may not be necessary  
cd python  
pip install -e . —verbose  

pip install numpy==1.16.2  
pip install gym  
pip install tensorflow-gpu==1.13.1 #gpu requires cuda 10; tensorflow cpu will also work, but is slower for minecraft experiments  
pip install opencv-python  
pip install torch  
pip install dm-sonnet==1.32  
pip install tensorflow-probability==0.6.0  
pip install git+https://github.com/deepmind/dnc.git  
pip install Pillow  
pip install pandas  
pip install matplotlib  
pip install seaborn  
pip install psutil  
pip install tornado  
pip install lz4  



# Notes:
-Ubuntu 18.04-LTS and 16.04-LTS should both be compatible with AMRL, with 18.04-LTS more thoroughly tested. Windows filesystems may cause errors.  
-If not specified, the version of pip installs should not matter. However, if you run into issues re-producing these experiments, you may want to try backdating the versions to July 2019 or February 2019. This issue did arise for Numpy building from source, and our best guess at the original version is therefore specified above.

# Commands:
\# A demo script that reproduces a couple results from the paper. (Should take under 3 days on a 6 CPU computer without GPU. Every multiple of 6 CPUs will decrease time. GPU should not affect speed much for demo, but will for full experiments.):  
**./demo_AMRL.sh**  
\# A script that should reproduces all results from the paper, but has not been tested after significant modification (to simplyify architecture implementation) due to limited compute budget. Note: The "set" model from the paper was left out in the architecture simplifications process, and more work may have to be done to make this script work on a cluster.    
**./full_AMRL_experimental.sh**  


## Contributing

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.opensource.microsoft.com.

When you submit a pull request, a CLA bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., status check, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

## Trademarks

This project may contain trademarks or logos for projects, products, or services. Authorized use of Microsoft 
trademarks or logos is subject to and must follow 
[Microsoft's Trademark & Brand Guidelines](https://www.microsoft.com/en-us/legal/intellectualproperty/trademarks/usage/general).
Use of Microsoft trademarks or logos in modified versions of this project must not cause confusion or imply Microsoft sponsorship.
Any use of third-party trademarks or logos are subject to those third-party's policies.
