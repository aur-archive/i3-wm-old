# Maintainer: Army <uli armbruster google>
# Contributor: Thorsten Töpper <atsutane-tu@freethoughts.de>

pkgname=i3-wm-old
_pkgsourcename=i3
pkgver=3.e_bf3
_pkgver=3.e-bf3
pkgrel=1
pkgdesc="An improved dynamic tiling window manager"
arch=('i686' 'x86_64')
url="http://i3.zekjur.net/"
license=('BSD')
conflicts=('i3-wm')
provides=('i3-wm')
depends=('libx11' 'xcb-util' 'libev' 'yajl' 'perl')
makedepends=('bison' 'flex')
optdepends=('rxvt-unicode: The terminal emulator used in the default config.'
            'dmenu: As menu.')
options=('docs' '!strip')
source=(http://i3.zekjur.net/downloads/${_pkgsourcename}-${_pkgver}.tar.bz2)
md5sums=('07a66e04bc754d0c16b033ed9df80c65')

build() {
  cd "$srcdir/$_pkgsourcename-$_pkgver"
  make
}

package() {
  cd "$srcdir/$_pkgsourcename-$_pkgver"
  make DESTDIR="$pkgdir/" install
  
  install -Dm644 man/i3.1 ${pkgdir}/usr/share/man/man1/i3.1
  install -Dm644 man/i3-msg.1 ${pkgdir}/usr/share/man/man1/i3-msg.1
  install -Dm644 man/i3-input.1 ${pkgdir}/usr/share/man/man1/i3-input.1
  install -Dm644 LICENSE ${pkgdir}/usr/share/licenses/${pkgname}/LICENSE
}
