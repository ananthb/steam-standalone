# Maintainer: Ananth Bhaskararaman 

pkgname=steam-standalone
pkgver=0.2
pkgrel=1
pkgdesc="Systemd service and user to run steam stand-alone in big picture mode"
# Arch ARM users do NOT attempt to use this package on Arch ARM!
# This is only for x86_64 and i686. You have been warned.
arch=('x86_64' 'i686')
license=('GPL')
depends=('systemd' 'xorg-server' 'xorg-xinit' 'steam' 'polkit' 'wmctrl' 'xfwm4')
install=readme.install
source=("https://github.com/ananthb/$pkgname/releases/download/$pkgver/files.tar.gz")
sha256sums=('cdd565f50a4b89719c73b403e4c552584428c4f77db2401f0eba794ab0396174')

package() {
	install -Dm644 "$srcdir/steam.service" \
		"$pkgdir/usr/lib/systemd/system/steam.service"
	install -Dm755 "$srcdir/steam-de" \
		"pkgdir/usr/bin/steam-de"
	install -dm 700 "$pkgdir"/var/lib/steam
	chown 540:540 "$pkgdir"/var/lib/steam
}
