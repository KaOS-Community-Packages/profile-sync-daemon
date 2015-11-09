pkgname='profile-sync-daemon'
pkgver=6.18
pkgrel=2
pkgdesc='Syncs browser profiles to tmpfs reducing SSD/HDD calls and speeding-up browsers.'
arch=('x86_64')
url='https://github.com/graysky2/profile-sync-daemon'
license=('MIT')
depends=('procps-ng' 'rsync' 'systemd')
optdepends=('firefox' 'google-chrome')
install=psd.install
source=("http://repo-ck.com/source/${pkgname}/${pkgname}-${pkgver}.tar.xz")
sha512sums=('04a8e9b026b0e362c9c0dd55102916171ac4eea70d529119367a25de2149008884a21e68720905b7d4f003516aa827b483c480ca2955216bc86011a6c0ea0186')

build() {
  cd "${pkgname}-${pkgver}"
  make
}

package() {
  cd "${pkgname}-${pkgver}"
  make DESTDIR="${pkgdir}" install
  install -Dm644 MIT "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
