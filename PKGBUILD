# Maintainer: artist for Sonic-DE

pkgname=sonic-screen
pkgver=6.6.4
_dirver=$(echo $pkgver | cut -d. -f1-3)
pkgrel=1
pkgdesc='Screen management software for SonicDE Workspaces'
arch=(x86_64)
url='https://github.com/Sonic-DE/sonic-screen'
license=(LGPL-2.0-or-later)
depends=(gcc-libs
         glibc
         kcmutils
         kconfig
         kcoreaddons
         kcrash
         kdbusaddons
         ki18n
         kimageformats
         kirigami
         kitemmodels
         ksvg
         libx11
         libxcb
         libxi
         plasma5support
         sonic-frameworks-windowsystem
         sonic-interface-libraries
         sonic-screen-library
         qt6-base
         qt6-declarative)
makedepends=(extra-cmake-modules)
groups=(sonicde)
conflicts=(kscreen)
provides=(kscreen)
replaces=(kscreen)
source=("$pkgname-$pkgver.tar.gz::${url}/archive/refs/tags/$pkgver.tar.gz")

build() {
  cmake -B build  -S $pkgname-$pkgver \
    -DBUILD_TESTING=OFF \
    -DCMAKE_INSTALL_LIBEXECDIR=lib
  cmake --build build
}

package() {
  DESTDIR="$pkgdir" cmake --install build
}

sha256sums=('ae26e96505f868e0cd3900f17889da79d44b58bdc11828edb6da305816e04f40')
