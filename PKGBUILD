# $Id$
# Maintainer: Jan de Groot <jgc@archlinux.org>
# Contributor: Sarah Hay <sarahhay@mb.sympatico.ca>

pkgname=ooo-thumbnailer-libgsf
_realpkgname=libgsf
pkgver=1.14.25
pkgrel=1
arch=(i686 x86_64)
pkgdesc="The GNOME Structured File Library is a utility library for reading and writing structured file formats"
url="http://www.gnome.org/"
license=('GPL' 'LGPL')
options=('!libtool')
depends=('libxml2' 'gdk-pixbuf2' 'bzip2')
conflicts=("libgsf-gnome<$pkgver" 'libgsf')
provides=("libgsf=$pkgver")
makedepends=('intltool' 'gobject-introspection')
source=(http://ftp.gnome.org/pub/GNOME/sources/$_realpkgname/1.14/$_realpkgname-$pkgver.tar.xz)
sha256sums=('127548f07e07951984fb139c3f89d65b9e471aefe6555387de03e1113944d1a2')

build() {
  cd "$srcdir/$_realpkgname-$pkgver"
  PYTHON=/usr/bin/python2 ./configure --prefix=/usr --sysconfdir=/etc \
      --localstatedir=/var --disable-static --enable-introspection
  make
}

package() {
  cd "$srcdir/$_realpkgname-$pkgver"
  make DESTDIR="$pkgdir" install

  rm -R "$pkgdir/usr/share/thumbnailers"
}
