# Maintainer: Chanathip Srithanrat <axesd9@gmail.com>

pkgname=macos11-icon-theme
pkgver=1.1
pkgrel=1
pkgdesc='macOS11 iCons Collection'
arch=('any')
url='https://www.opendesktop.org/p/1102582/'
license=('GPL')
depends=('gtk-update-icon-cache')

# Hash and Timestamp
_p="var \(hash = '\(.*\)\|timetamp = '\(.*\)\)';"
read _s _t <<< $(echo -n $(curl -s $url | sed -n "s/$_p/\2\3/p"))

source=("https://dl.opendesktop.org/api/files/downloadfile/id/1524703639/s/$_s/t/$_t/$pkgname-$pkgver.tar.xz")
md5sums=('cbe79976eb6371ebd4b5088f2784a91f')

prepare() {
    find -name '* *' -delete
    cp macOS11/status/symbolic/*.svg macOS11/devices/symbolic
    mv macOS11/apps/128/accessories_calculator.png macOS11/apps/128/accessories-calculator.png
}

package() {
    find */ -type f -exec install -Dm644 '{}' $pkgdir/usr/share/icons/'{}' \;
}
