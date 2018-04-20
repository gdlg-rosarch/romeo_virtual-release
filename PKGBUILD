# Script generated with Bloom
pkgdesc="ROS - The romeo_gazebo_plugin package"


pkgname='ros-kinetic-romeo-gazebo-plugin'
pkgver='0.2.3_1'
pkgrel=1
arch=('any')
license=('Apache 2.0'
)

makedepends=('ros-kinetic-catkin'
'ros-kinetic-gazebo-ros'
'ros-kinetic-romeo-description'
)

depends=('ros-kinetic-gazebo-plugins'
'ros-kinetic-gazebo-ros'
'ros-kinetic-gazebo-ros-control'
'ros-kinetic-romeo-control'
'ros-kinetic-romeo-description'
'ros-kinetic-ros-control'
'ros-kinetic-ros-controllers'
)

conflicts=()
replaces=()

_dir=romeo_gazebo_plugin
source=()
md5sums=()

prepare() {
    cp -R $startdir/romeo_gazebo_plugin $srcdir/romeo_gazebo_plugin
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

