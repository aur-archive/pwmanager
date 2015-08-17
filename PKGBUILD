# $Id: PKGBUILD 99966 2013-10-31 02:44:17Z allan $
# Maintainer: Sergej Pupykin <pupykin.s+arch@gmail.com>
# Maintainer: Vesa Kaihlavirta <vegai@iki.fi>
# Contributors: Pointer <pointer@linux-blog.de>, tmaynard <arch@toddmaynard.com>

pkgname=pwmanager
pkgver=1.2.4
pkgrel=5
pkgdesc="With PwManager you can easily manage your passwords"
arch=('i686' 'x86_64')
url="http://passwordmanager.sourceforge.net/"
license=('GPL')
depends=('kdelibs3')
source=(http://downloads.sourceforge.net/sourceforge/passwordmanager/$pkgname-$pkgver.tar.bz2
	build-fix.patch)
md5sums=('e6f720af9b325bc0e7ea20c9c5e6039f'
         'bcc412cb855cba4910e51920ae38a326')

build() {
  . /etc/profile.d/qt3.sh
  export PATH=$QTDIR/bin:$PATH
  cd $srcdir/$pkgname-$pkgver

  patch -p1 <$srcdir/build-fix.patch

  ./configure --prefix=/opt/kde --without-arts
  make
}

package() {
  cd $srcdir/$pkgname-$pkgver
  make DESTDIR=$pkgdir install
}
