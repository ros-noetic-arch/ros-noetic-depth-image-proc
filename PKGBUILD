# Script generated with import_catkin_packages.py.
# For more information: https://github.com/bchretien/arch-ros-stacks.
pkgdesc="ROS - Contains nodelets for processing depth images such as those produced by OpenNI camera."
url='https://wiki.ros.org/depth_image_proc'

pkgname='ros-noetic-depth-image-proc'
pkgver='1.17.0'
_pkgver_patch=0
arch=('i686' 'x86_64' 'aarch64' 'armv7h' 'armv6h')
pkgrel=2
license=('BSD')

ros_makedepends=(
	ros-noetic-tf2
	ros-noetic-image-geometry
	ros-noetic-nodelet
	ros-noetic-cmake-modules
	ros-noetic-stereo-msgs
	ros-noetic-catkin
	ros-noetic-cv-bridge
	ros-noetic-eigen-conversions
	ros-noetic-tf2-ros
	ros-noetic-message-filters
	ros-noetic-sensor-msgs
	ros-noetic-image-transport
)

makedepends=(
	'cmake'
	'ros-build-tools'
	${ros_makedepends[@]}
	boost
)

ros_depends=(
	ros-noetic-image-geometry
	ros-noetic-nodelet
	ros-noetic-cv-bridge
	ros-noetic-eigen-conversions
	ros-noetic-tf2-ros
	ros-noetic-tf2
	ros-noetic-image-transport
)

depends=(
	${ros_depends[@]}
	boost
)

_commit="69488e6e455d97c2deaf924234aa5f87b83cfda8"
_dir="image_pipeline-${_commit}/depth_image_proc"
source=("${pkgname}-${pkgver}.tar.gz"::"https://github.com/ros-perception/image_pipeline/archive/${_commit}.tar.gz")
sha256sums=('f833d69491a2b4988bafa1e4d74b539486853ddd9f184506d7e2c61e1b03fa85')

build() {
	# Use ROS environment variables.
	source /usr/share/ros-build-tools/clear-ros-env.sh
	[ -f /opt/ros/noetic/setup.bash ] && source /opt/ros/noetic/setup.bash

	# Create the build directory.
	[ -d ${srcdir}/build ] || mkdir ${srcdir}/build
	cd ${srcdir}/build

	# Build the project.
	cmake ${srcdir}/${_dir} \
		-DCATKIN_BUILD_BINARY_PACKAGE=ON \
		-DCMAKE_INSTALL_PREFIX=/opt/ros/noetic \
		-DPYTHON_EXECUTABLE=/usr/bin/python \
        -DCMAKE_CXX_STANDARD=17 \
		-DSETUPTOOLS_DEB_LAYOUT=OFF
	make
}

package() {
	cd "${srcdir}/build"
	make DESTDIR="${pkgdir}/" install
}
