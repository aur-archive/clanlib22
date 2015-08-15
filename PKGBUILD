 
# $Id$
# Contibuter: Sven-Hendrik Haase <sh@lutzhaase.com>
# Maintainer: Dany Martineau <dany.luc.martineau at gmail.com>

pkgname=clanlib22
pkgver=2.2.12
pkgrel=1
pkgdesc="A multi-platform game development library."
arch=('i686' 'x86_64')
url="http://clanlib.org/"
license=('zlib')
depends=('alsa-lib' 'libjpeg' 'libmikmod' 'libpng' 'libvorbis' 'libxi' 'libxmu' 'mesa' 'sdl_gfx' 'freetype2' 'pcre' 'sqlite3')
makedepends=('doxygen' 'graphviz')
options=('!libtool')
source=(http://clanlib.org/download/releases-2.0/ClanLib-${pkgver}.tgz)
md5sums=('1875b251f7ae6f5fae0750a2e85fa4f1')

build() { 
	cd ${srcdir}/ClanLib-${pkgver}

	./configure --prefix=/usr --enable-docs

	make
  # Somehow this breaks. :(
	#make html
}

package() {
	cd ${srcdir}/ClanLib-${pkgver}

	make DESTDIR=${pkgdir} install
	#make DESTDIR=${pkgdir} install-html

	install -d ${pkgdir}/usr/share/licenses/${pkgname}
	install -m644 COPYING ${pkgdir}/usr/share/licenses/${pkgname}/
}

# vim: sw=2:ts=2 et:
