# Script generated with Bloom
pkgdesc="ROS - A set of plugins for displaying occupancy information decoded from binary octomap messages."
url='http://ros.org/wiki/octomap_rviz_plugins'

pkgname='ros-kinetic-octomap-rviz-plugins'
pkgver='0.2.0_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-kinetic-catkin'
'ros-kinetic-octomap'
'ros-kinetic-octomap-msgs'
'ros-kinetic-roscpp'
'ros-kinetic-rviz'
)

depends=('ros-kinetic-octomap'
'ros-kinetic-octomap-msgs'
'ros-kinetic-roscpp'
'ros-kinetic-rviz'
)

conflicts=()
replaces=()

_dir=octomap_rviz_plugins
source=()
md5sums=()

prepare() {
    cp -R $startdir/octomap_rviz_plugins $srcdir/octomap_rviz_plugins
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

