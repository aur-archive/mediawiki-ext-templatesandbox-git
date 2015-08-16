# Maintainer: Felix E. xelif@icqmail.com

# Upstream name of extension:
_extname=TemplateSandbox
# Variant valid as package name:
_extpkgname=templatesandbox

pkgname=mediawiki-ext-$_extpkgname-git
pkgver=r233.df1cc1b
pkgrel=1
pkgdesc="A MediaWiki extension to develop templates in testing environment."
source=("git+https://gerrit.wikimedia.org/r/mediawiki/extensions/$_extname")
md5sums=("SKIP")
arch=("any")
url="http://www.mediawiki.org/wiki/Extension:$_extname"
license=("GPL")
depends=("mediawiki")
optdepends=("mediawiki-ext-scribunto-git: Supported scripting extension.")
makedepends=("git")
provides=("mediawiki-ext-$_extpkgname")
conflicts=()

pkgver() {
  cd $_extname
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

package() {
  # Target extension directory of MediaWiki:
  _extdir="$pkgdir/usr/share/webapps/mediawiki/extensions"
  mkdir -p "$_extdir"
  rsync -a $_extname "$_extdir/" --exclude .git
}