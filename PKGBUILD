
pkgname=a2jmidid
pkgver=9
pkgrel=1
pkgdesc="A daemon for exposing legacy ALSA sequencer applications in JACK MIDI system."
arch=('x86_64')
url="http://home.gna.org/$pkgname/"
license=('GPL2')
depends=('jack' 'dbus')
makedepends=('meson')
source=("https://github.com/linuxaudio/$pkgname/archive/$pkgver.tar.gz")
sha512sums=('5bd13b6904ed68c5bfe40ca516fd49b7eb4d4a946b9908ee04687265848734c8e1a81579f0f1a5bd0752595be8858dc748da10487b7f366394c09a5ffc7d5e5c')

build() {
  cd $pkgname-$pkgver
  meson --prefix=/usr build
  ninja -C build
}

package() {
  cd $pkgname-$pkgver
  DESTDIR="${pkgdir}" meson install -C build
  install -vDm 644 {AUTHORS,CHANGELOG,INSTALLATION,README}.rst \
    -t "${pkgdir}/usr/share/doc/${pkgname}"
}
