# $Id$
# Maintainer: BlackIkeEagle <ike DOT devolder AT gmail DOT com>
# Contributor: Cedric Girard <girard.cedric@gmail.com>

pkgname=p8-platform
pkgver=2.0.1
pkgrel=2
pkgdesc="Platform support library used by libCEC and binary add-ons for Kodi"
arch=('i686' 'x86_64')
url="https://github.com/Pulse-Eight/platform"
license=('GPL')
conflicts=('libplatform')
replaces=('libplatform')
makedepends=('cmake')
depends=('gcc-libs')
source=(https://github.com/Pulse-Eight/platform/archive/p8-platform-${pkgver}.tar.gz)
sha256sums=('e97e45273e90571aa37732cde913b262f5f519c387083645d2557d7189c054cf')

build() {
  cd "$srcdir"/platform-p8-platform-${pkgver}
  cmake . \
    -DCMAKE_BUILD_TYPE=Release \
    -DBUILD_SHARED_LIBS=1 \
    -DCMAKE_INSTALL_PREFIX=/usr \
    -DCMAKE_INSTALL_LIBDIR=/usr/lib \
    -DCMAKE_INSTALL_LIBDIR_NOARCH=/usr/lib
  make
}

package() {
  cd "$srcdir"/platform-p8-platform-${pkgver}
  make DESTDIR="$pkgdir/" install
}

# vim:set ts=2 sw=2 et:
