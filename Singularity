Bootstrap: docker
From: nvidia/cuda:7.5-cudnn5-devel-ubuntu14.04

%post

    # Update list of available packages, then upgrade them
    apt-get update
    DEBIAN_FRONTEND=noninteractive apt-get -y upgrade
    # Update list of packages and install packages for ease of use.
    apt-get update
    apt-get install -y apt-utils
    apt-get install -y vim
    apt-get install -y tmux screen
    apt-get install -y xterm
	
    # Install for tkinter
    apt-get install -y python-tk
    #Install dependencies for caffe
    apt-get install -y libxcb-xfixes0-dev
    apt-get install -y libgflags-dev libgoogle-glog-dev liblmdb-dev
    
    # OpenCV from pip, including contrib.  This makes the install MUCH faster.
    # See https://pypi.python.org/pypi/opencv-contrib-python for capabilities 
    # and limitations.  
    pip install --no-cache-dir opencv-contrib-python

    # Installing imutils,dlib,progressbar for FACES projectt
    pip install --no-cache-dir imutils
    pip install --no-cache-dir dlib
    pip install --no-cache-dir progressbar2
    pip install --no-cache-dir lmdb
    pip install --no-cache-dir flask
    pip install --no-cache-dir flask_cors
    pip install --no-cache-dir sklearn
    
    git clone https://github.com/MehdiNoroozi/JigsawPuzzleSolver.git
    cd caffe-master-jps++
    cp Makefile.config.example Makefile.config
    # Adjust Makefile.config (for example, if using Anaconda Python, or if cuDNN is desired)
    make all
    make test
    make runtest
    
