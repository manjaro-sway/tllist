# Maintainer: lmartinez
pkgname=tllist
pkgver=1.0.5
pkgrel=2
pkgdesc="A typed linked list C header file only library"
arch=('x86_64' 'aarch64')
url="https://codeberg.org/dnkl/tllist"
license=('MIT')
makedepends=('git' 'meson' 'ninja')
source=("$pkgname-$pkgver.tar.gz::$url/archive/$pkgver.tar.gz")
sha512sums=('e8d55a727de56956c6823297e92ba4656292096ece7d22f3d8834b86811ede9b2fdca580bea55e0beda35322f418140357770592d85c0c07ea09c1642c7ff1e9')

build() {
  cd "$pkgname"
  meson --prefix=/usr --buildtype=release build
  ninja -C build
}

package() {
  cd "$pkgname"
  DESTDIR="$pkgdir/" ninja -C build install
  install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
