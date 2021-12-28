# Maintainer: Sergio Marzana <sergiomarzana1@gmai.com>
pkgname=slock-custom
pkgver=1.4
pkgrel=1
epoch=0
pkgdesc="A (customized) simple screen locker for X"
arch=('x86_64')
url="https://tools.suckless.org/slock"
license=('MIT')
depends=('libxext' 'libxrandr')
conflicts=('slock')
replaces=('slock')
source=("git+https://github.com/ndfsa/slock.git")
sha256sums=('SKIP')

build() {
	cd "$srcdir/slock"
	make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11
}

package() {
	cd "$srcdir/slock"
	make PREFIX=/usr DESTDIR="$pkgdir/" install
	install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
