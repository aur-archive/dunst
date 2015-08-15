# vim:set ts=2 sw=2 et:
# Maintainer: feuri

pkgname=dunst
pkgver=0.3.1
pkgrel=1
pkgdesc="a dmenu-ish notification system "
arch=(i686 x86_64)
url="http://knopwob.github.com/dunst"
license=(MIT)
depends=(dbus-core libxinerama libxft libxss libxdg-basedir)
makedepends=('git' 'perl')
optdepends=('libnotify: dunst is able to listen to notifications from libnotify')
provides=(notification-daemon)
source=(${pkgname}-${pkgver}.tar.gz::https://github.com/knopwob/${pkgname}/tarball/v${pkgver})

build() {
	cd "${srcdir}"
	mv knopwob-dunst-* ${pkgname}
	cd "${pkgname}"
	
	make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11
}

package() {
	cd "${srcdir}/${pkgname}"
	make DESTDIR=${pkgdir} PREFIX=/usr install
	install -Dm644 "${srcdir}/${pkgname}/LICENSE" "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
md5sums=('9cf4890fc6fafbdb98c8db4f54dea194')
