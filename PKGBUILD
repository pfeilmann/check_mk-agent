# Maintainer 2016-2017: Milian Reichardt <mreichardt95@gmail.com>
# Maintainer since 2018: Christian Blechert <christian@anysrc.net>

pkgname=check_mk-agent
pkgver=1.5.0p16
pkgrel=3
pkgdesc="Agent to send information to a Check_MK server"
arch=(any)
url="https://mathias-kettner.de"
license=('GPLv2')
install=${pkgname}.install
depends=('xinetd')

source=("check_mk_agent.linux::https://raw.githubusercontent.com/tribe29/checkmk/v${pkgver}/agents/check_mk_agent.linux"
        "check_mk_caching_agent.linux::https://raw.githubusercontent.com/tribe29/checkmk/v${pkgver}/agents/check_mk_caching_agent.linux"
        "xinetd.conf::https://raw.githubusercontent.com/tribe29/checkmk/v${pkgver}/agents/cfg_examples/xinetd.conf")

sha512sums=('978050b2ec6b15e0389911178eb9d8eed459fb043299043ac89b7463d3f6a7cbd3de8b9d3dd21883e5c3002c1e0ca9c486ff9b9faecb9c6f024812373b0ce3fa'
            'cd1e9c1de50e523fc602249b052fa90470e41665bf61a87117b02733eea6d5b4c7dc1c1c8500f5d2a56a4707ac2ffd8a9d147a35b67c877436b221d88aa8b16a'
            '2a27edb4f16e2cc6e6c3523675f0f98c3bd6ff842478dbeeb0a6f6d48c0b2632bdba9ddf0215928ab6fa15c1c03d2ae5ccfef4f28b43b9cd2915e8ea47855667')

package() {
	mkdir -p "$pkgdir/usr/bin/"
	mkdir -p "$pkgdir/etc/xinetd.d/"
	mkdir -p "$pkgdir/var/lib/check_mk_agent/cache"
	mkdir -p "$pkgdir/var/lib/check_mk_agent/job"
	mkdir -p "$pkgdir/var/lib/check_mk_agent/spool"
	mkdir -p "$pkgdir/usr/lib/check_mk_agent/local"
	mkdir -p "$pkgdir/usr/lib/check_mk_agent/plugins"
	install -m744 "$srcdir/check_mk_agent.linux" "$pkgdir/usr/bin/check_mk_agent"
	install -m644 "$srcdir/xinetd.conf" "$pkgdir/etc/xinetd.d/check_mk"
	install -m744 "$srcdir/check_mk_caching_agent.linux" "$pkgdir/usr/bin/check_mk_caching_agent"
}

