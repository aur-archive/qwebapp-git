# Maintainer: Zatherz <zatherz[at]linux[dot]com>
pkgname=qwebapp-git
pkgver=r0.gae98fb8
pkgrel=1
pkgdesc="Fast and slick customizable minimalistic web browser used for making desktop launchers for web apps."
url="http://github.com/Zatherz/qwebapp/"
arch=('x86_64' 'i686')
license=('GPLv2')
depends=('qt5-base' 'qt5-webkit')
makedepends=('git')
source=("git://github.com/Zatherz/qwebapp")
md5sums=("SKIP")

pkgver() {
  cd "qwebapp"
  git describe --long --all | sed -r 's/([^-]*-g)/r\1/;s/-/./g;s/heads\/master.//g'
}

build() {
  cd "qwebapp"
  mkdir build
  cd build
  qmake ..
  make
}

package() {
  cd "qwebapp"
  install -Dm755 build/qwebapp "$pkgdir/usr/bin/qwebapp"
  install -Dm664 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
