# Script generated with Bloom
pkgdesc="ROS - Tile map provides a slippy map style interface for visualizing OpenStreetMap and GooleMap tiles. A mapviz visualization plug-in is also implemented"
url='https://github.com/swri-robotics/mapviz'

pkgname='ros-lunar-tile-map'
pkgver='0.2.5_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('jsoncpp'
'qt5-base'
'ros-lunar-catkin'
'ros-lunar-mapviz'
'ros-lunar-pluginlib'
'ros-lunar-roscpp'
'ros-lunar-swri-math-util'
'ros-lunar-swri-transform-util'
'ros-lunar-swri-yaml-util'
'ros-lunar-tf'
)

depends=('jsoncpp'
'qt5-base'
'ros-lunar-mapviz'
'ros-lunar-pluginlib'
'ros-lunar-roscpp'
'ros-lunar-swri-math-util'
'ros-lunar-swri-transform-util'
'ros-lunar-swri-yaml-util'
'ros-lunar-tf'
)

conflicts=()
replaces=()

_dir=tile_map
source=()
md5sums=()

prepare() {
    cp -R $startdir/tile_map $srcdir/tile_map
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

