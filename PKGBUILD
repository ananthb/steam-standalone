# Maintainer: Ananth Bhaskararaman 

pkgname=steam-standalone
pkgver=0.1
pkgrel=1
pkgdesc="Systemd service and user to run steam stand-alone in big picture mode"
# Arch ARM users do NOT attempt to use this package on Arch ARM!
# This is only for x86_64 and i686. You have been warned.
arch=('x86_64' 'i686')
license=('GPL')
depends=('systemd' 'xorg-server' 'xorg-xinit' 'steam' 'polkit')
install=readme.install
source=("https://github.com/ananthb/$pkgname/archive/v$pkgver.tar.gz")
sha256sums=('a165a66e976bb1a6ac622618887c2f9699acd84d8790af517b85a66bf5e0474c')

package() {
	install -Dm644 "$srcdir/$pkgname-$pkgver/steam.service" \
		"$pkgdir/usr/lib/systemd/system/steam.service"
	install -dm 700 "$pkgdir"/var/lib/steam
	chown 540:540 "$pkgdir"/var/lib/steam
}
