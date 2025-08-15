pkgname=newsfy-git
pkgver=r8.9031e02  # This will be set dynamically; replace with actual if needed
pkgrel=1
pkgdesc="Terminal-based viewer for the most recent Arch Linux news"
arch=('x86_64')
url="https://github.com/ruplume/newsfy"
license=('unknown')
depends=('curl' 'ncurses' 'w3m')
optdepends=('firefox: for viewing articles in browser'
'chromium: for viewing articles in browser')
makedepends=('git' 'gcc')
provides=('newsfy')
conflicts=('newsfy')
source=("git+${url}.git")
sha256sums=('SKIP')
install=newsfy.install
pkgver() {
cd "${srcdir}/${pkgname%-git}"
printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}
build() {
cd "${srcdir}/${pkgname%-git}/src"
g++ newsfy.cpp -o newsfy -lcurl -lncurses
}
package() {
cd "${srcdir}/${pkgname%-git}"
install -Dm755 src/newsfy "${pkgdir}/usr/bin/newsfy"
}
