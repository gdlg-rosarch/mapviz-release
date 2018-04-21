# Script generated with Bloom
pkgdesc="ROS - mapviz"
url='https://github.com/swri-robotics/mapviz'

pkgname='ros-kinetic-mapviz'
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
'ros-kinetic-catkin'
'ros-kinetic-cv-bridge'
'ros-kinetic-image-transport'
'ros-kinetic-marti-common-msgs'
'ros-kinetic-message-generation'
'ros-kinetic-pluginlib'
'ros-kinetic-rosapi'
'ros-kinetic-roscpp'
'ros-kinetic-rqt-gui'
'ros-kinetic-rqt-gui-cpp'
'ros-kinetic-std-srvs'
'ros-kinetic-swri-transform-util'
'ros-kinetic-swri-yaml-util'
'ros-kinetic-tf'
)

depends=('freeglut'
'glew'
'libxi'
'libxmu'
'qt5-base'
'ros-kinetic-cv-bridge'
'ros-kinetic-image-transport'
'ros-kinetic-marti-common-msgs'
'ros-kinetic-message-runtime'
'ros-kinetic-pluginlib'
'ros-kinetic-rosapi'
'ros-kinetic-roscpp'
'ros-kinetic-rqt-gui'
'ros-kinetic-rqt-gui-cpp'
'ros-kinetic-std-srvs'
'ros-kinetic-swri-transform-util'
'ros-kinetic-swri-yaml-util'
'ros-kinetic-tf'
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
  [ -f /opt/ros/kinetic/setup.bash ] && source /opt/ros/kinetic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/kinetic \
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

