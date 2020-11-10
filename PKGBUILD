# Maintainer 2016-2017: Milian Reichardt <mreichardt95@gmail.com>
# Maintainer since 2018: Christian Blechert <christian@anysrc.net>

pkgname=check_mk-agent
pkgver=1.6.0
pkgrel=1
pkgdesc="Agent to send information to a Check_MK server"
arch=(any)
url="https://mathias-kettner.de"
license=('GPLv2')
install=${pkgname}.install

source=("check_mk_agent.linux::https://raw.githubusercontent.com/tribe29/checkmk/v${pkgver}/agents/check_mk_agent.linux"
        "check_mk_caching_agent.linux::https://raw.githubusercontent.com/tribe29/checkmk/v${pkgver}/agents/check_mk_caching_agent.linux"
        "check_mk-agent.service::https://raw.githubusercontent.com/tribe29/checkmk/v${pkgver}/agents/cfg_examples/systemd/check_mk%40.service"
        "check_mk-agent.socket::https://raw.githubusercontent.com/tribe29/checkmk/v${pkgver}/agents/cfg_examples/systemd/check_mk.socket")

sha512sums=('dd74e65041f37c02af647abae55d1572c5fd27267b491082d67d3c4f00266e46da481c71822fa6b97f2a119116ff14e180e93c3d703fba0e3aeee335548494a7'
            'a165bc7a7a1be4941f25b476b9a433c8b67994afc7689271f26fb21a2a2b89e95609086d3d80da017527b470c7b0bf948a6dbd97a764e4875603a7ceb905e02e'
            '2ca8f5f621483da7a66c8e4651f85b80ec140406cfbc704559c40a115e4b059e1dda06f5b18fe06a1669274dbd0bcadced4876629e1385135a05eadc5dd3aa70'
            '1bfd04e8e999a0a5abca36d385430006f3579cce2de9eeca265e026219fc985a67a445f6ab2b3b57b843bd20a0169f33322537527d1e0fa64cfd80f3273622d3')

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
}
