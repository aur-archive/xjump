# $Id: PKGBUILD,v 1.12 2003/11/06 08:26:13 dorphell Exp $
# Packager: Martin Frost <blamefrost@gmail.com>
# Maintainer: Vitor Sakaguti <vitoreiji0 at gmail.com>
# Contributor: Martin Frost <blamefrost@gmail.com>
pkgname=xjump
pkgver=2.7.5 
pkgrel=5
pkgdesc="A jumping game for X. Very simple, yet very addictive"
arch=('i686' 'x86_64')
url="http://www.foo.org"
license=('GPL')
groups=
provides=()
depends=('libxaw' 'glibc')
makedepends=('libxaw')
install='xjump.install'
source=(http://ftp.debian.org/debian/pool/main/x/xjump/xjump_$pkgver.orig.tar.gz)
md5sums=('3e8d09c6b8162b7e4380f8a77eb595dc')

build() {
  tar -xzf "$pkgname"_$pkgver.orig.tar.gz
  sed -i "s/\/usr\/games/\/usr\/bin/" $pkgname-$pkgver.orig/Makefile
  cd $srcdir/$pkgname-$pkgver.orig

#  ./configure --prefix=/usr
  make || return 1
}
package() {
  cd $srcdir/$pkgname-$pkgver.orig
  mkdir -p $pkgdir/usr/bin
  mkdir -p $pkgdir/var/games/xjump
  chmod 775 $pkgdir/var/games
  make DESTDIR="$pkgdir" install
}
