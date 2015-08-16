# Maintainer: Daniel Stumpner <bigstumpi@gmx.de>
# Contributor: SpepS <dreamspepser at yahoo dot it>

pkgname=llcon
pkgver=3.2.1
pkgrel=1
pkgdesc="Low-Latency (Internet) Connection tool for real-time jam sessions"
arch=(i686 x86_64)
url="http://sourceforge.net/projects/llcon/"
license=('GPL2')
depends=('qt' 'jack')
install="$pkgname.install"
source=("http://downloads.sourceforge.net/project/$pkgname/$pkgname/$pkgver/$pkgname-$pkgver.tar.gz"
        "$pkgname.png::http://a.fsdn.com/con/icons/ll/llcon@sf.net/MediaWikiSidebarLogo.png"
        "$pkgname.desktop")
md5sums=('4d03805a67b28479649e91abb95cabce'
         'b3f350f2f98861f2b0738d3b4ceecae7'
         '6f099fc9c300ad9487b544b461b15df9')

build() {
  cd "$srcdir/$pkgname"*

  qmake llcon.pro
  make
}

package() {
  cd "$srcdir/$pkgname"*

  # bin
  install -Dm755 $pkgname "$pkgdir/usr/bin/llcon"

  # desktop file
  install -Dm644 ../$pkgname.desktop \
    "$pkgdir/usr/share/applications/$pkgname.desktop"

  # icon
  install -Dm644 ../$pkgname.png \
    "$pkgdir/usr/share/pixmaps/$pkgname.png"
}
