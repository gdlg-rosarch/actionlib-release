# Script generated with Bloom
pkgdesc="ROS - The actionlib stack provides a standardized interface for interfacing with preemptable tasks. Examples of this include moving the base to a target location, performing a laser scan and returning the resulting point cloud, detecting the handle of a door, etc."
url='http://www.ros.org/wiki/actionlib'

pkgname='ros-kinetic-actionlib'
pkgver='1.11.13_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('boost'
'ros-kinetic-actionlib-msgs'
'ros-kinetic-catkin>=0.5.78'
'ros-kinetic-message-generation'
'ros-kinetic-roscpp'
'ros-kinetic-rosnode'
'ros-kinetic-rospy'
'ros-kinetic-rostest'
'ros-kinetic-std-msgs'
)

depends=('boost'
'ros-kinetic-actionlib-msgs'
'ros-kinetic-message-runtime'
'ros-kinetic-roscpp'
'ros-kinetic-roslib'
'ros-kinetic-rospy'
'ros-kinetic-rostest'
'ros-kinetic-rostopic'
'ros-kinetic-std-msgs'
'wxpython'
)

conflicts=()
replaces=()

_dir=actionlib
source=()
md5sums=()

prepare() {
    cp -R $startdir/actionlib $srcdir/actionlib
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

