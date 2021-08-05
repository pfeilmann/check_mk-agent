# Maintainer 2016-2017: Milian Reichardt <mreichardt95@gmail.com>
# Maintainer since 2018: Christian Blechert <christian@anysrc.net>

pkgname=check_mk-agent
pkgver=2.0.0p8
commit=cfb9f38b0199cc6ce18a3a525239815e12f2e288
pkgrel=1
pkgdesc="Agent to send information to a Check_MK server"
arch=(any)
url="https://mathias-kettner.de"
license=('GPLv2')
install=${pkgname}.install

source=("check_mk_agent.linux::https://raw.githubusercontent.com/tribe29/checkmk/v${pkgver}/agents/check_mk_agent.linux"
        "check_mk_caching_agent.linux::https://raw.githubusercontent.com/tribe29/checkmk/v${pkgver}/agents/check_mk_caching_agent.linux"
        "check_mk-agent.service::https://raw.githubusercontent.com/tribe29/checkmk/${commit}/agents/cfg_examples/systemd/check_mk%40.service"
        "check_mk-agent.socket::https://raw.githubusercontent.com/tribe29/checkmk/${commit}/agents/cfg_examples/systemd/check_mk.socket"
        "check_mk-agent-async.service::https://raw.githubusercontent.com/tribe29/checkmk/${commit}/agents/cfg_examples/systemd/check_mk-async.service"
        )

sha512sums=('b846b9b72801623b5ce7cf7a0a096d37fc0e2cf736439a281ee0557972eaecbd9061add478ed9d95c4d7f931ed5e80bc0ee0703188f3f52a872879dba00dc5b2'
            'cfbf17d67b0295c428aa528529f8acec995311e9490e64c4b764c06cd8234c1e8008618e6684c11ebe93c07452942af1c5911e21dda7c02b4bed5dd4f3d0f123'
            '788e192794ae2c076ac377c17094c405ec0faddf4471dbc54c380c8b4591a3abda7d95d489bf1d9bd67787408babe92a491c05d36e7945a70847c3afd9d54ff9'
            '8f78f0e047a71966ad3c73cf9240cdba1414b4d56608c6333543d8d8744fc86eef1135257e905a52644415ffc7656b6600f8562cbd598ec7bf02ef794e2fa242'
            '82743efae6f604c0f9bf3283a12f33e731dcd04623f48a501b331d99bff27b8905550ea76f0b2c22fa9fe5382a58440a2f6ab9b47e8bbefb6d9951e62cb77a60')

package() {
	mkdir -p "$pkgdir/usr/bin/"
	mkdir -p "$pkgdir/var/lib/check_mk_agent/cache"
	mkdir -p "$pkgdir/var/lib/check_mk_agent/job"
	mkdir -p "$pkgdir/var/lib/check_mk_agent/spool"
	mkdir -p "$pkgdir/usr/lib/check_mk_agent/local"
	mkdir -p "$pkgdir/usr/lib/check_mk_agent/plugins"
	mkdir -p "$pkgdir/etc/systemd/system"
	install -m744 "$srcdir/check_mk_agent.linux" "$pkgdir/usr/bin/check_mk_agent"
	install -m744 "$srcdir/check_mk_caching_agent.linux" "$pkgdir/usr/bin/check_mk_caching_agent"
	install -m644 "$srcdir/check_mk-agent.service" "$pkgdir/etc/systemd/system/check_mk-agent@.service"
	install -m644 "$srcdir/check_mk-agent.socket" "$pkgdir/etc/systemd/system/check_mk-agent.socket"
	install -m644 "$srcdir/check_mk-agent-async.service" "$pkgdir/etc/systemd/system/check_mk-agent-async.service"
}
