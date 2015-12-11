# This is an example PKGBUILD file. Use this as a start to creating your own,
# and remove these comments. For more information, see 'man PKGBUILD'.
# NOTE: Please fill out the license field for your package! If it is unknown,
# then please put 'unknown'.

# Maintainer: Your Name <youremail@domain.com>
pkgname=monacoin
pkgver=0.10.2.2
pkgrel=1
pkgdesc="peer to peer crypto currency Monacoin full client."
arch=('i686' 'x86_64')
url="http://monacoin.org/"
license=('MIT')
depends=('boost-libs' 'qt4' 'qrencode' 'protobuf' 'db4.8')
makedepends=('boost' 'qrencode' 'protobuf')
source=("https://github.com/monacoinproject/monacoin/archive/v$pkgver-hotfix.tar.gz")
md5sums=('cffdf0e505820b62fe8104c9c47d8fa9')

build() {
	cd "$srcdir/$pkgname-$pkgver-hotfix"
  ./autogen.sh
	./configure
  make
}

package() {
	cd "$srcdir/$pkgname-$pkgver-hotfix"
#	make DESTDIR="$pkgdir/" install
  install -Dm755 src/qt/monacoin-qt "$pkgdir"/usr/bin/monacoin-qt
  install -Dm755 src/monacoind "$pkgdir"/usr/bin/monacoind
  install -Dm755 src/monacoin-cli "$pkgdir"/usr/bin/monacoin-cli
  install -Dm755 src/monacoin-tx "$pkgdir"/usr/bin/monacoin-tx
  install -Dm644 share/pixmaps/bitcoin128.png "$pkgdir"/usr/share/pixmaps/monacoin128.png
  install -Dm644 COPYING "$pkgdir/usr/share/licenses/$pkgname/COPYING"
}
