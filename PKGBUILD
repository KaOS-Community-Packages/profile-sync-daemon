pkgname=profile-sync-daemon
pkgver=6.36
pkgrel=1
pkgdesc='Symlinks and syncs browser profile dirs to RAM'
arch=('x86_64')
url='https://github.com/graysky2/profile-sync-daemon'
license=('MIT')
depends=('bash' 'findutils' 'procps-ng' 'rsync' 'systemd')
install="${pkgname}.install"
source=("$pkgname-$pkgver.tar.gz::https://github.com/graysky2/$pkgname/archive/v$pkgver.tar.gz")
sha512sums=('c292ec499a598e13b29122dc6bb3dffd7151f6540d84c6821b9960febfefc13f9bff302e89dcdd599c35f29198f6fdb7981a938b3e088cd502511db1c07b6a6d')

build() {
  cd "$pkgname-$pkgver"
  make
}

package() {
  cd "$pkgname-$pkgver"
  make DESTDIR="$pkgdir/" install
  install -vDm 644 MIT "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
  install -vDm 644 README.md -t "${pkgdir}/usr/share/doc/${pkgname}"
  }
