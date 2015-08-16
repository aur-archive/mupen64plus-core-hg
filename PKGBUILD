# Contributer: BeholdMyGlory <larvid@gmail.com>
pkgname=mupen64plus-core-hg
pkgver=609
pkgrel=2
pkgdesc="Core of Mupen64Plus v2.0, a Nintendo 64 emulator. Latest hg pull."
url="http://bitbucket.org/richard42/mupen64plus-core"
license=("GPL")
arch=(i686 x86_64)
groups=(mupen64plus-hg)
depends=(sdl libpng mesa freetype2)
makedepends=(mercurial glproto dri2proto)
source=("hg+http://bitbucket.org/richard42/mupen64plus-core")
md5sums=('SKIP')

pkgver() {
	cd $srcdir/${pkgname%-*}
	echo $(hg identify -n)
}

build() {
	cd "${srcdir}/${pkgname%-*}"
	make -C projects/unix all
}

package() {
	cd "${srcdir}/${pkgname%-*}"
	mkdir -p "${pkgdir}/usr/lib"
	mkdir -p "${pkgdir}/usr/share/mupen64plus"
	mkdir -p "${pkgdir}/usr/include/mupen64plus"
	cp -P "projects/unix/"*.so.* "${pkgdir}/usr/lib"
	cp "data/"* "${pkgdir}/usr/share/mupen64plus"
	cp "src/api/"m64p_*.h "${pkgdir}/usr/include/mupen64plus"
}
