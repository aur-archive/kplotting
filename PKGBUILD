# Maintainer: Andrea Scarpino <andrea@archlinux.org>

pkgname=kplotting
pkgver=4.99.0
pkgrel=1
pkgdesc='KPlotting'
arch=('i686' 'x86_64')
url='https://projects.kde.org/projects/frameworks/kplotting'
license=('LGPL')
depends=('qt5-base')
makedepends=('extra-cmake-modules')
groups=('kf5')
source=("http://download.kde.org/unstable/frameworks/${pkgver}/${pkgname}-${pkgver}.tar.xz")
md5sums=('e1d4a2f75b3dcd97ef80979e2310d7ff')

prepare() {
  mkdir -p build
}

build() {
  cd build
  cmake ../${pkgname}-${pkgver} \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/opt/kf5 \
    -DLIB_INSTALL_DIR=lib \
    -DBUILD_TESTING=OFF
  make
}

package() {
  cd build
  make DESTDIR="${pkgdir}" install
}
