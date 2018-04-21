# Script generated with Bloom
pkgdesc="ROS - Common plugins for the Mapviz visualization tool"
url='https://github.com/swri-robotics/mapviz'

pkgname='ros-kinetic-mapviz-plugins'
pkgver='0.2.5_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('qt5-base'
'ros-kinetic-actionlib'
'ros-kinetic-catkin'
'ros-kinetic-cv-bridge'
'ros-kinetic-gps-common'
'ros-kinetic-image-transport'
'ros-kinetic-mapviz'
'ros-kinetic-marti-common-msgs'
'ros-kinetic-marti-nav-msgs'
'ros-kinetic-marti-visualization-msgs'
'ros-kinetic-move-base-msgs'
'ros-kinetic-nav-msgs'
'ros-kinetic-pluginlib'
'ros-kinetic-roscpp'
'ros-kinetic-sensor-msgs'
'ros-kinetic-std-msgs'
'ros-kinetic-stereo-msgs'
'ros-kinetic-swri-image-util'
'ros-kinetic-swri-math-util'
'ros-kinetic-swri-route-util'
'ros-kinetic-swri-transform-util'
'ros-kinetic-swri-yaml-util'
'ros-kinetic-tf'
'ros-kinetic-visualization-msgs'
)

depends=('qt5-base'
'ros-kinetic-actionlib'
'ros-kinetic-cv-bridge'
'ros-kinetic-gps-common'
'ros-kinetic-image-transport'
'ros-kinetic-mapviz'
'ros-kinetic-marti-common-msgs'
'ros-kinetic-marti-nav-msgs'
'ros-kinetic-marti-visualization-msgs'
'ros-kinetic-move-base-msgs'
'ros-kinetic-nav-msgs'
'ros-kinetic-pluginlib'
'ros-kinetic-roscpp'
'ros-kinetic-sensor-msgs'
'ros-kinetic-std-msgs'
'ros-kinetic-stereo-msgs'
'ros-kinetic-swri-image-util'
'ros-kinetic-swri-math-util'
'ros-kinetic-swri-route-util'
'ros-kinetic-swri-transform-util'
'ros-kinetic-swri-yaml-util'
'ros-kinetic-tf'
'ros-kinetic-visualization-msgs'
)

conflicts=()
replaces=()

_dir=mapviz_plugins
source=()
md5sums=()

prepare() {
    cp -R $startdir/mapviz_plugins $srcdir/mapviz_plugins
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

