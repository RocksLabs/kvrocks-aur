# This is an example PKGBUILD file. Use this as a start to creating your own,
# and remove these comments. For more information, see 'man PKGBUILD'.
# NOTE: Please fill out the license field for your package! If it is unknown,
# then please put 'unknown'.

# Maintainer: PragmaTwice <twice.mliu@gmail.com>
pkgname=kvrocks
pkgver=2.3.0
pkgrel=1
epoch=
pkgdesc="A distributed key value NoSQL database that uses RocksDB as storage engine and compatible with Redis protocol"
arch=(any)
url="https://kvrocks.apache.org/"
license=('Apache')
groups=()
depends=(libunwind)
makedepends=(python git gcc make cmake autoconf automake libtool)
checkdepends=()
optdepends=()
provides=()
conflicts=()
replaces=()
backup=()
options=()
install=
changelog=
source=("$pkgname-$pkgver.tar.gz::https://github.com/apache/incubator-kvrocks/archive/refs/tags/v2.3.0.tar.gz")
noextract=()
sha256sums=('6a57c28430b884a634aaa5524b9013b4e6664eded4567e11ab206ed98797e80a')
validpgpkeys=()

prepare() {
	mv incubator-$pkgname-$pkgver $pkgname-$pkgver || true
	cd $pkgname-$pkgver
}

build() {
	cd $pkgname-$pkgver
	./x.py build -j$(nproc)
}

check() {
	cd $pkgname-$pkgver
}

package() {
	cd $pkgname-$pkgver/build
	mkdir -p $pkgdir/usr/bin
	cp kvrocks $pkgdir/usr/bin
	cp kvrocks2redis $pkgdir/usr/bin
	mkdir -p $pkgdir/usr/share/kvrocks
	cp ../kvrocks.conf $pkgdir/usr/share/kvrocks
}

