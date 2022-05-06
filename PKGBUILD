# Maintainer: Jonathan Schilling <jonathan.schilling@mail.de>
pkgname=inkscape
pkgver=0.92.5
pkgrel=1
pkgdesc="Vector drawing program"
arch=(x86_64)
url="https://inkscape.org/release/inkscape-0.92.5/"
license=('GPL')
provides=(inkscape)
source=("https://inkscape.org/gallery/item/18051/$pkgname-$pkgver.tar.bz2"
        "$pkgname-$pkgver.patch")
md5sums=(592c0e94cf00ea9e0a8901883d8f06fd
         2d203d3497e1c474560b12b9d47d52f5)

prepare() {
	cd "$pkgname-$pkgver"
	patch -p1 -i "$srcdir/$pkgname-$pkgver.patch"
}

build() {
	cd "$pkgname-$pkgver"
	mkdir build
	cd build
	cmake -DCMAKE_INSTALL_PREFIX=/usr ..
	make
}

package() {
	cd "$pkgname-$pkgver"/build
	make DESTDIR="$pkgdir/" install
}

