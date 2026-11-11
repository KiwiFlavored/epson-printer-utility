pkgname=epson-printer-utility
pkgver=1.2.3
pkgrel=1
pkgdesc='Epson Printer Utility for Linux
 This is a Printer Utility program for Epson Printer Driver.
 Using this software, you can check ink levels, view error and other status... on EPSON Printers.
 For detail list of supported printer, please refer to below site:
 http://download.ebz.epson.net/dsc/search/01/search/?OSC=LX'
arch=('x86_64')
url='https://download-center.epson.com/'
license=('LGPL-2.1-only' 'LicenseRef-COPYING')
options=('strip')
depends=('libusb' 'qt5-base')
install="$pkgname.install"
source=("${pkgname}_${pkgver}-1_amd64.deb"
		'LICENSE'
		"$pkgname.install")
sha256sums=('6b9e462d1b7764cf74dbbb9964f9dd9230f415a7be5c735133b5966157ecf86f'
			'4646fe05bf8d375f284fa5ba47e9a13b4c0cbf5d8ac56ddbc3f1789ab0d19956'
			'cfdff952e847c701c0b568d416fed0d1dc15c1aafbb12baa439d658eefbd3478')

prepare() {
	[ -d data ] && rm -rf data
	mkdir data
	cd data
	for datatar in ../data.tar.*; do
		echo "Unpacking $datatar"
		tar -xf $datatar
	done
}

package() {
	
	cp -a "$srcdir"/data/opt "$pkgdir"
	install -dm 755 "$pkgdir"/usr/
	cp -a "$srcdir"/data/usr/lib "$pkgdir"/usr
	install -dm 755 "$pkgdir"/usr/share/licenses/"$pkgname"
	install -Dm 644 "$srcdir"/data/usr/share/doc/{COPYING,COPYING.fr} "$pkgdir"/usr/share/licenses/"$pkgname"

}