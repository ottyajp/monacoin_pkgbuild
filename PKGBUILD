# Maintainer: Your Name <youremail@domain.com>
pkgname=monacoin-qt
pkgver=0.10.2.2
pkgrel=1
pkgdesc="peer to peer crypto currency Monacoin (QT)"
arch=('i686' 'x86_64')
url="http://monacoin.org/"
license=('MIT')
depends=('boost-libs' 'qt4' 'qrencode' 'protobuf')
install=monacoin-qt.install
source=("https://github.com/monacoinproject/monacoin/archive/v$pkgver-hotfix.tar.gz"
        "$pkgname.desktop")
md5sums=('cffdf0e505820b62fe8104c9c47d8fa9'
         '8de4bc1a7922cdf682e26f6c168f13fd')

build() {
  cd "$srcdir/monacoin-$pkgver-hotfix"
  ./autogen.sh
  ./configure \
    --without-miniupnpc \
    --with-incompatible-bdb \
    #--with-gui=qt5 \
    #--without-gui \
    #--enable-upnp-default \
    #--disable-wallet

  make
}

package() {
  install -Dm644 monacoin-qt.desktop "$pkgdir"/usr/share/applications/monacoin.desktop
  cd "$srcdir/monacoin-$pkgver-hotfix"
#	make DESTDIR="$pkgdir/" install
  install -Dm755 src/qt/monacoin-qt "$pkgdir"/usr/bin/monacoin-qt
  install -Dm755 src/monacoind "$pkgdir"/usr/bin/monacoind
  install -Dm755 src/monacoin-cli "$pkgdir"/usr/bin/monacoin-cli
  install -Dm755 src/monacoin-tx "$pkgdir"/usr/bin/monacoin-tx
  install -Dm644 share/pixmaps/bitcoin128.png "$pkgdir"/usr/share/pixmaps/monacoin128.png
  install -Dm644 COPYING "$pkgdir/usr/share/licenses/$pkgname/COPYING"
}
