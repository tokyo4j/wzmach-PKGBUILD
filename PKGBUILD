pkgname=wzmach-git
pkgver=1.1.0.r17.28ae40d
pkgrel=1
arch=('x86_64')
pkgdesc="A Linux daemon for keypad gestures"
url="https://github.com/tokyo4j/wzmach"
license=('MIT')
makedepends=(git cargo)
optdepends=()
provides=("${pkgname%-git}")
conflicts=("${pkgname%-git}")
source=('git+https://github.com/tokyo4j/wzmach' 'wzmach.service')
sha256sums=('SKIP' 'SKIP')
backup=('etc/wzmach/config.ron')

pkgver() {
	cd "${srcdir}/${pkgname%-git}"
	git describe --long --tags | sed -E '
		s/([^-]*-)g/r\1/
		s/-/./g
		s/^v//
	'
}

build() {
	cd "${srcdir}/${pkgname%-git}"
	cargo build --release
}

package() {
	cd "${srcdir}/${pkgname%-git}"
    make PREFIX="${pkgdir}/usr/bin" CONFIG_PREFIX="${pkgdir}/etc" install

    install -Dm644 "${srcdir}/wzmach.service" -t "${pkgdir}/usr/lib/systemd/system/"
}
