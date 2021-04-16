pkgname=slock
pkgver=1.5
pkgrel=1
pkgdesc="A simple screen locker for X"
arch=('x86_64')
url="https://tools.suckless.org/slock"
license=('MIT')
depends=('libxext' 'libxrandr')
#source=("https://dl.suckless.org/tools/$pkgname-$pkgver.tar.gz")
#source=("slock-$pkgver.tar.bz2::https://hg.suckless.org/slock/archive/$_pkgver.tar.gz")
#md5sums=('f91dd5ba50ce7bd1842caeca067086a3')
source=("https://github.com/jemgoss/$pkgname/archive/refs/tags/v$pkgver.tar.gz")
md5sums=("489b05843b0164a07388b0fab4b5a966")
#
#prepare() {
#}

build() {
  cd "$srcdir/$pkgname-$pkgver"
  make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11
}

package() {
  cd "$srcdir/$pkgname-$pkgver"
  make PREFIX=/usr DESTDIR="$pkgdir" install
  install -m644 -D LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
