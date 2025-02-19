pkgname=fatx
pkgver=1.18
_tag=17d7403f0b23fa43cd71e90cf22273ae7f53c9db
pkgrel=1
pkgdesc='XBox filesystem support for linux'
arch=('i686' 'pentium4' 'armv7h' 'aarch64' 'x86_64')
url='http://sourceforge.net/projects/fatx/'
license=('GPL')
provides=($pkgname)
depends=('fuse')
makedepends=('boost' 'boost-libs' 'doxygen')
source=("git+https://git.code.sf.net/p/fatx/code#tag=$_tag"
    'fatx.patch')
sha256sums=('SKIP'
    'SKIP')

build() {
    patch -p0 -d "${srcdir}"/code <"${srcdir}"/fatx.patch
    mkdir -p "${srcdir}"/code/build
    cd "${srcdir}"/code/build
    cmake ../ -DCMAKE_INSTALL_PREFIX:PATH=/usr
    make
}

package() {
    cd "${srcdir}"/code/build
    make DESTDIR="$pkgdir" install
}
