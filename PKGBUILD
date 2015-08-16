# $Id: PKGBUILD 226492 2014-11-19 17:36:28Z fyan $
# Maintainer: Andrea Scarpino <andrea@archlinux.org>

pkgname=kdebindings-perlkde
pkgver=4.14.3
pkgrel=1
pkgdesc="Perl bindings for the KDE libraries"
url="https://projects.kde.org/projects/kde/kdebindings/perl/perlkde"
arch=('i686' 'x86_64')
license=('GPL' 'LGPL' 'FDL')
groups=('kdebindings')
depends=('kdebindings-perlqt' 'kdebindings-smokekde')
makedepends=('cmake' 'automoc4' 'kdebindings-smokegen' 'kdepimlibs'
             'kdegraphics-okular' 'kdesdk-kate')
source=("http://download.kde.org/stable/${pkgver}/src/perlkde-${pkgver}.tar.xz")
sha1sums=('2b7900342b5a87e08e256b8943498407743c336f')

prepare() {
  mkdir build
}

build() {
  cd build
  cmake ../perlkde-${pkgver} \
    -DCMAKE_BUILD_TYPE=Release \
    -DKDE4_BUILD_TESTS=OFF \
    -DCMAKE_SKIP_RPATH=ON \
    -DCMAKE_INSTALL_PREFIX=/usr \
    -DWITH_Soprano=OFF \
    -DWITH_Nepomuk=OFF
  make
}

package() {
  cd build
  make DESTDIR="${pkgdir}" install
}
