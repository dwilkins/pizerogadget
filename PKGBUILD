# Maintainer: Your Name <dwilkins@conecuh.com>
pkgname=pizerogadget
pkgver=0.0.1
pkgrel=1
epoch=
pkgdesc="Configuration to use the Raspberry Pi Zero as an ethernet gadget"
arch=('armv6')
url=""
license=('GPL')
groups=()
depends=('linux-raspberrypi>=4.4' 'dhcp>=4.3.4')
makedepends=()
checkdepends=()
optdepends=()
provides=()
conflicts=()
replaces=()
backup=( 'etc/dhcpd.conf' 'boot/config.txt' 'etc/modules-load.d/raspberrypi.conf' 'etc/modprobe.d/g_ether.conf' )
options=()
install=
changelog=
source=("$pkgname-$pkgver.tar.gz"
        "$pkgname-$pkgver.patch")
noextract=()
md5sums=()
validpgpkeys=()

prepare() {
	cd "$pkgname-$pkgver"
	patch -p1 -i "$srcdir/$pkgname-$pkgver.patch"
}

build() {
	cd "$pkgname-$pkgver"
	./configure --prefix=/usr
	make
}

check() {
	cd "$pkgname-$pkgver"
	make -k check
}

package() {
	cd "$pkgname-$pkgver"
	make DESTDIR="$pkgdir/" install
}
