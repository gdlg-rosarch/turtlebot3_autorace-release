# Script generated with Bloom
pkgdesc="ROS - TurtleBot3 AutoRace ROS package that controls TurtleBot3 Auto"
url='http://wiki.ros.org/turtlebot3_autorace_control'

pkgname='ros-kinetic-turtlebot3-autorace-control'
pkgver='1.0.0_1'
pkgrel=1
arch=('any')
license=('Apache 2.0'
)

makedepends=('ros-kinetic-catkin'
)

depends=('python2-enum34'
'python2-numpy'
'ros-kinetic-geometry-msgs'
'ros-kinetic-nav-msgs'
'ros-kinetic-rospy'
'ros-kinetic-sensor-msgs'
'ros-kinetic-std-msgs'
'ros-kinetic-tf'
)

conflicts=()
replaces=()

_dir=turtlebot3_autorace_control
source=()
md5sums=()

prepare() {
    cp -R $startdir/turtlebot3_autorace_control $srcdir/turtlebot3_autorace_control
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

