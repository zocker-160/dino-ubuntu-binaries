# Maintainer: zocker_160 <zocker1600 at posteo dot net>

pkgname=dino
pkgver=0.4.2
pkgrel=1
pkgdesc="Dino - Modern Jabber/XMPP Client using GTK+/Vala"
arch=('x86_64')
url="https://dino.im/"
license=('GPL3')
_base_depends=('libc6' 'libcairo2' 'libgcc-s1' 'libgcrypt20' 'libgdk-pixbuf2.0-0'
        'libgee-0.8-2' 'libglib2.0-0' 'libgnutls30' 'libgpg-error0' 'libgpgme11'
        'libgspell-1-2' 'libgstreamer-plugins-base1.0-0' 'libgstreamer1.0-0' 'libgtk-4-1' 'libadwaita-1-0'
        'libnice10' 'libpango-1.0-0' 'libqrencode4' 'libsoup2.4-1'
        'libsqlite3-0' 'libsrtp2-1' 'libstdc++6' 'libwebrtc-audio-processing1' 'glib-networking'
        'gstreamer1.0-plugins-good' 'gstreamer1.0-gtk3' 'libsrtp2-1')
depends=("${_base_depends[@]}" 'libicu66')
jammy_depends=("${_base_depends[@]}" 'libicu70')
bullseye_depends=("${_base_depends[@]}" 'libicu67')
makedepends=('git' 'cmake' 'g++' 'ninja-build' 'valac' 'gettext' 'libgee-0.8-dev' 'libsqlite3-dev' 'libgtk-4-dev' 'libadwaita-1-dev'
        'libgpgme-dev' 'libsoup2.4-dev' 'libgcrypt20-dev' 'libqrencode-dev' 'libgspell-1-dev' 'libgstreamer1.0-dev'
        'libgstreamer-plugins-base1.0-dev' 'libwebrtc-audio-processing-dev' 'libsrtp2-dev' 'libnice-dev' 'glib-networking'
        'gstreamer1.0-plugins-good' 'gstreamer1.0-gtk3' 'libsignal-protocol-c-dev' 'libsrtp2-dev')

conflicts=('dino' 'dino-im' 'dino-im-common' 'dino-plugin-http-files' 'dino-plugin-omemo' 'dino-plugin-openpgp' 'libdino0'
            'libqlite0' 'libxmpp-vala0')
provides=('dino' 'dino-im' 'dino-im-common' 'dino-plugin-http-files' 'dino-plugin-omemo' 'dino-plugin-openpgp' 'libdino0'
            'libqlite0' 'libxmpp-vala0')
source=("$pkgname-$pkgver::https://github.com/dino/dino/releases/download/v$pkgver/dino-$pkgver.tar.gz")
sha256sums=('SKIP')

build() {
    cd ${srcdir}/${pkgname}-${pkgver}
    ./configure --with-libsignal-in-tree --prefix="/usr"
    make -j$(nproc)
}

package() {
    cd ${srcdir}/${pkgname}-${pkgver}
    make DESTDIR="${pkgdir}" prefix="/usr" install
}
