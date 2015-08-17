# custom variables
_hkgname=splot
_licensefile=LICENSE

# PKGBUILD options/directives
pkgname=splot
pkgver=0.2.7
pkgrel=2
pkgdesc="A tool for visualizing the lifecycle of many concurrent multi-staged processes."
url="http://www.haskell.org/haskellwiki/Splot"
license=("BSD3")
arch=('i686' 'x86_64')
makedepends=("ghc=7.0.3-2"
             "haskell-chart=0.14-23"
             "haskell-hunit=1.2.2.3-2.1"
             "haskell-bytestring-lexing=0.2.1-19"
             "haskell-cairo=0.12.1-2"
             "haskell-colour=2.3.1-18"
             "haskell-mtl=2.0.1.0-3.1"
             "haskell-strptime=1.0.2-1")
depends=()
options=('strip')
source=("http://hackage.haskell.org/packages/archive/${_hkgname}/${pkgver}/${_hkgname}-${pkgver}.tar.gz")

sha256sums=("40186b6ef8b6639451ab9e333645269dba8c60c3f7a522ae2ff90495e9e81252")

# PKGBUILD functions
build() {
    cd ${srcdir}/${_hkgname}-${pkgver}
    
    runhaskell Setup configure -O --prefix=/usr --docdir=/usr/share/doc/${pkgname}
    runhaskell Setup build
}

package() {
    cd ${srcdir}/${_hkgname}-${pkgver}
    runhaskell Setup copy --destdir=${pkgdir}
}
