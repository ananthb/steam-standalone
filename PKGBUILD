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
source=("https://github.com/ananthb/$pkgname/releases/download/$pkgver/files.tar.gz")
sha256sums=('f2a2de40be790e92cdbfea4fd5b88395f904e7e689905c9c95dc781c63e49a46')

package() {
	install -Dm644 "$srcdir/$pkgname-$pkgver/steam.service" \
		"$pkgdir/usr/lib/systemd/system/steam.service"
	install -dm 700 "$pkgdir"/var/lib/steam
	chown 540:540 "$pkgdir"/var/lib/steam
}
