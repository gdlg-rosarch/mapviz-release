# Script generated with Bloom
pkgdesc="ROS - Common plugins for the Mapviz visualization tool"
url='https://github.com/swri-robotics/mapviz'

pkgname='ros-lunar-mapviz-plugins'
pkgver='0.2.5_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('qt5-base'
'ros-lunar-actionlib'
'ros-lunar-catkin'
'ros-lunar-cv-bridge'
'ros-lunar-gps-common'
'ros-lunar-image-transport'
'ros-lunar-mapviz'
'ros-lunar-marti-common-msgs'
'ros-lunar-marti-nav-msgs'
'ros-lunar-marti-visualization-msgs'
'ros-lunar-move-base-msgs'
'ros-lunar-nav-msgs'
'ros-lunar-pluginlib'
'ros-lunar-roscpp'
'ros-lunar-sensor-msgs'
'ros-lunar-std-msgs'
'ros-lunar-stereo-msgs'
'ros-lunar-swri-image-util'
'ros-lunar-swri-math-util'
'ros-lunar-swri-route-util'
'ros-lunar-swri-transform-util'
'ros-lunar-swri-yaml-util'
'ros-lunar-tf'
'ros-lunar-visualization-msgs'
)

depends=('qt5-base'
'ros-lunar-actionlib'
'ros-lunar-cv-bridge'
'ros-lunar-gps-common'
'ros-lunar-image-transport'
'ros-lunar-mapviz'
'ros-lunar-marti-common-msgs'
'ros-lunar-marti-nav-msgs'
'ros-lunar-marti-visualization-msgs'
'ros-lunar-move-base-msgs'
'ros-lunar-nav-msgs'
'ros-lunar-pluginlib'
'ros-lunar-roscpp'
'ros-lunar-sensor-msgs'
'ros-lunar-std-msgs'
'ros-lunar-stereo-msgs'
'ros-lunar-swri-image-util'
'ros-lunar-swri-math-util'
'ros-lunar-swri-route-util'
'ros-lunar-swri-transform-util'
'ros-lunar-swri-yaml-util'
'ros-lunar-tf'
'ros-lunar-visualization-msgs'
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

