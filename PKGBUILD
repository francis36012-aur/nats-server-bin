# Maintainer: Francis Agyapong <francisagyapong2 at gmail dot com>

_pkgname="nats-server"
pkgname="${_pkgname}-bin"
pkgdesc="Simple, secure and high performance open source messaging system"
pkgver=2.10.17
pkgrel=1
provides=("${_pkgname}=${pkgver}")
conflicts=("${_pkgname}")
arch=("x86_64")
url="https://nats.io"
license=("Apache")
source=(
	"https://github.com/nats-io/nats-server/releases/download/v$pkgver/nats-server-v$pkgver-linux-amd64.zip"
	"local://nats-server.service"
)

sha256sums=(
	"1c526214479d1e2c370f880f05835068d961897d0d0389dbdf238b359c2161a5"
	"6b46575f585ef0b8415c5b71592b3cb2aee9fc93447e043a5f92033513199a5a"
)

package() {
	local actual_srcdir="$srcdir/$_pkgname-v$pkgver-linux-amd64"

	install -Dm 755 "${actual_srcdir}/nats-server" -t "${pkgdir}/usr/bin"
	install -Dm 644 "${srcdir}/nats-server.service" -t "${pkgdir}/usr/lib/systemd/system"
	install -Dm 644 "${actual_srcdir}/README.md" -t "${pkgdir}/usr/share/doc/${_pkgname}"
}
