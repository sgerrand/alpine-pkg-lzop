# Contributor: Sasha Gerrand <alpine-pkgs@sgerrand.com>
# Maintainer: Sasha Gerrand <alpine-pkgs@sgerrand.com>
pkgname=lzop
pkgver=1.04
pkgrel=0
pkgdesc="lzop is a very fast file compressor"
url="https://www.lzop.org/"
arch="all"
license="GPL2"
depends="lzo"
depends_dev=""
makedepends="$depends_dev autoconf gcc lzo-dev make"
install=""
subpackages="$pkgname-doc"
source="https://www.lzop.org/download/lzop-$pkgver.tar.gz"
builddir="$srcdir/$pkgname-$pkgver"

build() {
	cd "$builddir"
	./configure \
		--build=$CBUILD \
		--host=$CHOST \
		--prefix=/usr \
		--sysconfdir=/etc \
		--mandir=/usr/share/man \
		--localstatedir=/var
	make
}

check() {
	cd "$builddir"
	make check
}

package() {
	cd "$builddir"
	make DESTDIR="$pkgdir" install
	install -Dm644 COPYING "$pkgdir"/usr/share/licenses/$pkgname/COPYING
}

sha512sums="5829b4495ffefab549aa697a05c536ce593c572c9eee6004460583a0090abcd317c6074c4f981dfee6be61ac8d127f02dd37053b6cb782af64db41586a8bbb6e  lzop-1.04.tar.gz"
