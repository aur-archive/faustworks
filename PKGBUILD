## Maintainer: rtfreedman (rob<d0t>til<d0t>freedman<aT>gmail<d0t>com
## Contributor: SpepS <dreamspepser at yahoo dot it>
pkgname=faustworks
pkgver=0.5
pkgrel=1
pkgdesc="An IDE for DSP programming with Faust"
arch=('i686' 'x86_64')
url="http://faust.grame.fr/"
license=('GPL')
depends=('faust' 'qt4')
install="$pkgname.install"
source=("http://downloads.sourceforge.net/project/faudiostream/FaustWorks-$pkgver.zip")
md5sums=('5ec624215f5b5da6fe3f7fd03e6cb80e')
noextract=("FaustWorks-$pkgver.zip")

prepare() {
  unzip -d FaustWorks FaustWorks-$pkgver.zip
}

build() {
  cd FaustWorks
  # we have qt3, qt4 and 'stupid' qt defaults to qt5
  sed -i 's/lrelease/lrelease-qt4/' FaustWorks.pro
  qmake-qt4
  make
}

package() {
  cd FaustWorks
  #install -Dm644 Resources/translations/i18n_ru.qm "$pkgdir"/usr/share/faustworks/translations/i18n_ru.qm
  install -Dm755 FaustWorks "$pkgdir/usr/bin/$pkgname"
  install -Dm644 $pkgname.desktop "$pkgdir/usr/share/applications/$pkgname.desktop"
  install -Dm644 Resources/$pkgname.png "$pkgdir/usr/share/pixmaps/$pkgname.png"
}
