# https://tecadmin.net/how-to-install-opencv-on-ubuntu-20-04/
# git \
```
sudo apt install \
    build-essential \
    cmake \
    pkg-config \
    libpng-dev \
    libtiff-dev \
    gfortran \
    openexr \
    libgtk-3-dev \
    libavcodec-dev \
    libgstreamer-plugins-base1.0-dev \
    libgstreamer1.0-dev \
    libavformat-dev \
    libswscale-dev \
    libv4l-dev \
    libxvidcore-dev \
    libx264-dev \
    libjpeg-dev \
    libatlas-base-dev \
    python3-dev \
    python3-numpy \
    libtbb2 \
    libtbb-dev \
    libdc1394-22-dev \
    libopenexr-dev 
```
```
sudo apt-get install libopencv-core-dev
```
```
mkdir ~/opencv_build && cd ~/opencv_build 
git clone https://github.com/opencv/opencv.git 
git clone https://github.com/opencv/opencv_contrib.git 
```
```
cd ~/opencv_build/opencv 
mkdir -p build && cd build
```
```
cmake \
    -D CMAKE_BUILD_TYPE=RELEASE \
    -D CMAKE_INSTALL_PREFIX=/home/ubuntu/.venv/opencv_test \
    -D PYTHON_DEFAULT_EXECUTABLE=$(which python) \
    -D PYTHON3_EXECUTABLE=$(which python) \
    -D PYTHON_INCLUDE_DIR=$(python -c "from distutils.sysconfig import get_python_inc; print(get_python_inc())") \
    -D PYTHON_INCLUDE_DIR2=$(python -c "from os.path import dirname; from distutils.sysconfig import get_config_h_filename; print(dirname(get_config_h_filename()))") \
    -D PYTHON_LIBRARY=$(python -c "from distutils.sysconfig import get_config_var;from os.path import dirname,join ; print(join(dirname(get_config_var('LIBPC')),get_config_var('LDLIBRARY')))") \
    -D PYTHON3_NUMPY_INCLUDE_DIRS=$(python -c "import numpy; print(numpy.get_include())") \
    -D PYTHON3_PACKAGES_PATH=$(python -c "from distutils.sysconfig import get_python_lib; print(get_python_lib())") \
    -D BUILD_NEW_PYTHON_SUPPORT=ON \
    -D BUILD_opencv_python3=ON \
    -D HAVE_opencv_python3=ON \
    -D INSTALL_PYTHON_EXAMPLES=ON \
    -D BUILD_EXAMPLES=OFF \
    -D OPENCV_GENERATE_PKGCONFIG=ON \
    -D OPENCV_EXTRA_MODULES_PATH=~/opencv_build/opencv_contrib/modules \
    -D INSTALL_C_EXAMPLES=ON ..
```
```
nproc
make -j4
sudo make install
pkg-config --modversion opencv4
python -c "import cv2; print(cv2.__version__)"
```
```
/home/ubuntu/.venv/opencv_test
source ~/.venv/opencv_test/bin/activate
```
# -D BUILD_PERF_TESTS=OFF \
```
cmake \
    -D CMAKE_BUILD_TYPE=RELEASE \
    -D CMAKE_INSTALL_PREFIX=/home/ubuntu/.venv/opencv_test \
    -D PYTHON_DEFAULT_EXECUTABLE=$(which python) \
    -D PYTHON3_EXECUTABLE=$(which python) \
    -D PYTHON_INCLUDE_DIR=$(python -c "from distutils.sysconfig import get_python_inc; print(get_python_inc())") \
    -D PYTHON_LIBRARY=$(python -c "from distutils.sysconfig import get_config_var;from os.path import dirname,join ; print(join(dirname(get_config_var('LIBPC')),get_config_var('LDLIBRARY')))") \
    -D BUILD_opencv_python3=ON \
    -D BUILD_NEW_PYTHON_SUPPORT=ON \
    -D HAVE_opencv_python3=ON \
    -D INSTALL_PYTHON_EXAMPLES=ON \
    -D BUILD_EXAMPLES=OFF \
    -D OPENCV_GENERATE_PKGCONFIG=ON \
    -D OPENCV_EXTRA_MODULES_PATH=~/opencv_build/opencv_contrib/modules \
    -D INSTALL_C_EXAMPLES=ON ..
```
```
cmake \
    -D CMAKE_BUILD_TYPE=RELEASE \
    -D CMAKE_INSTALL_PREFIX=/home/ubuntu/.venv/opencv_test \
    -D PYTHON_DEFAULT_EXECUTABLE=$(which python) \
    -D PYTHON3_EXECUTABLE=$(which python) \
    -D PYTHON_INCLUDE_DIR=$(python -c "from distutils.sysconfig import get_python_inc; print(get_python_inc())") \
    -D PYTHON_INCLUDE_DIR2=$(python -c "from os.path import dirname; from distutils.sysconfig import get_config_h_filename; print(dirname(get_config_h_filename()))") \
    -D PYTHON_LIBRARY=$(python -c "from distutils.sysconfig import get_config_var;from os.path import dirname,join ; print(join(dirname(get_config_var('LIBPC')),get_config_var('LDLIBRARY')))") \
    -D PYTHON3_NUMPY_INCLUDE_DIRS=$(python -c "import numpy; print(numpy.get_include())") \
    -D PYTHON3_PACKAGES_PATH=$(python -c "from distutils.sysconfig import get_python_lib; print(get_python_lib())") \
    -D BUILD_NEW_PYTHON_SUPPORT=ON \
    -D BUILD_opencv_python3=ON \
    -D HAVE_opencv_python3=ON \
    -D INSTALL_PYTHON_EXAMPLES=ON \
    -D BUILD_EXAMPLES=OFF \
    -D OPENCV_GENERATE_PKGCONFIG=ON \
    -D OPENCV_EXTRA_MODULES_PATH=~/opencv_build/opencv_contrib/modules \
    -D INSTALL_C_EXAMPLES=ON ..
```

https://www.swiftlane.com/blog/generating-mp4s-using-opencv-python-with-the-avc1-codec/


sudo mount /
