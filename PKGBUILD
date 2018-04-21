# Script generated with Bloom
pkgdesc="ROS - mapviz"
url='https://github.com/swri-robotics/mapviz'

pkgname='ros-lunar-mapviz'
pkgver='0.2.5_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('freeglut'
'glew'
'libxi'
'libxmu'
'pkg-config'
'qt5-base'
'ros-lunar-catkin'
'ros-lunar-cv-bridge'
'ros-lunar-image-transport'
'ros-lunar-marti-common-msgs'
'ros-lunar-message-generation'
'ros-lunar-pluginlib'
'ros-lunar-rosapi'
'ros-lunar-roscpp'
'ros-lunar-rqt-gui'
'ros-lunar-rqt-gui-cpp'
'ros-lunar-std-srvs'
'ros-lunar-swri-transform-util'
'ros-lunar-swri-yaml-util'
'ros-lunar-tf'
)

depends=('freeglut'
'glew'
'libxi'
'libxmu'
'qt5-base'
'ros-lunar-cv-bridge'
'ros-lunar-image-transport'
'ros-lunar-marti-common-msgs'
'ros-lunar-message-runtime'
'ros-lunar-pluginlib'
'ros-lunar-rosapi'
'ros-lunar-roscpp'
'ros-lunar-rqt-gui'
'ros-lunar-rqt-gui-cpp'
'ros-lunar-std-srvs'
'ros-lunar-swri-transform-util'
'ros-lunar-swri-yaml-util'
'ros-lunar-tf'
)

conflicts=()
replaces=()

_dir=mapviz
source=()
md5sums=()

prepare() {
    cp -R $startdir/mapviz $srcdir/mapviz
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/lunar/setup.bash ] && source /opt/ros/lunar/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/lunar \
        -DPYTHON_EXECUTABLE=/usr/bin/python2 \
        -DPYTHON_INCLUDE_DIR=/usr/include/python2.7 \
        -DPYTHON_LIBRARY=/usr/lib/libpython2.7.so \
        -DPYTHON_BASENAME=-python2.7 \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}

