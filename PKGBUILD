# Maintainer: artist for Sonic-DE

pkgname=sonic-screen
pkgver=6.6.5
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

sha256sums=('c32c825529a69b30d81beeccce834a48bcc8e922401473210d922024693c6d1a')
