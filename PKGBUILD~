# Maintainer: Brenton Horne <brentonhorne77 at gmail dot com>
# Contributor: Michael Corrigan <ghost.vonage AT gmail DOT com>
# Contributor: tomsik68	<tomsik68 AT gmail DOT com>
# Contributor: gandl <gandlspam AT gmail DOT com>
# Contributor: Jristz <prflr88 AT gmail DOT com>
# Upstream URL: http://messengerfordesktop.com/

pkgname=messengerfordesktop-bin
_pkgname=Facebook-Messenger-Desktop
pkgver=2.0.1
pkgrel=1
pkgdesc="Beautiful desktop client for Facebook Messenger. Chat without being distracted by your feed or notifications."
arch=('i686' 'x86_64')
url="http://messengerfordesktop.com/"
license=('MIT')
options=(!strip)
conflicts=("messengerfordesktop")
provides=("messengerfordesktop")
depends=('cairo' 'libxtst' 'alsa-lib' 'gtk2' 'gconf' 'libnotify' 'fontconfig' 'nss')
install=$pkgname.install
depends=('gcc-libs' 'cairo' 'libxtst' 'alsa-lib' 'gtk2' 'gconf' 'libnotify' 'fontconfig' 'nss' 'xorg-xprop' 'xorg-xwininfo')
source_i686=("https://github.com/Aluxian/Facebook-Messenger-Desktop/releases/download/v$pkgver/messengerfordesktop-$pkgver-linux-i386.deb")
source_x86_64=("https://github.com/Aluxian/Facebook-Messenger-Desktop/releases/download/v$pkgver/messengerfordesktop-$pkgver-linux-amd64.deb")
md5sums_i686=('ec21ded143c6b71b61aefd16b1e700b9')
md5sums_x86_64=('8381f7aa9a7aa6eafbd925185860549c')
install="$pkgname.install"

prepare() {
  bsdtar -xf data.tar.gz
}

package() {
  cd $srcdir
	mkdir -p "${pkgdir}/opt/messengerfordesktop"
	cp -r "opt/messengerfordesktop/"* "${pkgdir}/opt/messengerfordesktop"

	install -Dm644 "usr/share/applications/messengerfordesktop.desktop" \
			"${pkgdir}/usr/share/applications/messengerfordesktop.desktop"
	install -Dm644 "usr/share/icons/hicolor/512x512/apps/messengerfordesktop.png" \
      "${pkgdir}/usr/share/pixmaps/messengerfordesktop.png"
	install -Dm644 "opt/messengerfordesktop/LICENSE" \
			"${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"

}
