pkgname=haskell-pandoc-crossref-bin
_pkgname=pandoc-crossref
pkgver=0.3.8.3
_pandoc_pkgver=2.11.0.2
pkgrel=1
pkgdesc="Pandoc filter for cross-references - executable only"
url="https://hackage.haskell.org/package/${_pkgname}"
license=("GPL2")
arch=('x86_64')
conflicts=("pandoc-crossref")
provides=("pandoc-crossref")
replaces=('pandoc-crossref-bin' 'pandoc-crossref-static' 'pandoc-crossref-lite')
depends=("pandoc-bin>=${_pandoc_pkgver}")

source=(
    "pandoc-crossref-${pkgver}.tar.xz::https://github.com/lierdakil/pandoc-crossref/releases/download/v${pkgver}/pandoc-crossref-Linux.tar.xz"
)
sha256sums=('3e2a1b1cf43bdfeba3ad954b14f1ea69dddac435a8da154a412c74633c03f883')

package() {
    cd "${srcdir}"

    # To avoid having to download over a gigabyte of haskell makedepends (400-ish for ghc, plus 750 in libs), we
    # just yoink the binary from static compiled binary distributed by pandoc:
    mkdir -p "${pkgdir}/usr/bin"
    cp pandoc-crossref "${pkgdir}/usr/bin/"
    mkdir -p "${pkgdir}/usr/share/man/man1/"
    cp pandoc-crossref.1 "${pkgdir}/usr/share/man/man1/"
}
