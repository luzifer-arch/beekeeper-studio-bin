# Maintainer: Knut Ahlers <knut@ahlers.me>
# Contributor: Sitansh Rajput <me [at] lostpolaris [dot] com>
# Contributor: Caltlgin Stsodaat <contact@fossdaily.xyz>
# Contributor: Michael Lutonsky <m@luto.at>
# Contributor: Tássio Virgínio <tassiovirginio@gmail.com>

pkgname='beekeeper-studio-bin'
pkgver=4.2.9
pkgrel=1
pkgdesc='Modern and easy to use SQL client for MySQL, Postgres, SQLite, SQL Server, and more'
arch=('x86_64' 'aarch64')
url='https://www.beekeeperstudio.io'
license=('MIT')
depends=('libappindicator-gtk3' 'libnotify' 'libsecret' 'libxss' 'libxslt' 'nodejs' 'nss' 'xdg-utils')
provides=(beekeeper-studio)
conflicts=(beekeeper-studio)
source=("beekeeper-studio-${pkgver}-license::https://github.com/beekeeper-studio/beekeeper-studio/raw/v${pkgver}/LICENSE.md")
source_x86_64=("https://github.com/beekeeper-studio/beekeeper-studio/releases/download/v${pkgver}/beekeeper-studio_${pkgver}_amd64.deb")
source_aarch64=("https://github.com/beekeeper-studio/beekeeper-studio/releases/download/v${pkgver}/beekeeper-studio_${pkgver}_arm64.deb")
sha256sums=('1409fbbc5265c85da91684660c87f85d74c3fdc63a2d355169f40dac5cc7a078')
sha256sums_x86_64=('dd427ba6592683943c358b8bea8ea52edc3f03a56dcb0f93d6fb3da760b89887')
sha256sums_aarch64=('5e26d0ce5832c7b44ab1a4f3deed88c49c62f299a869f2d7352f1c876225b667')

package() {
  tar -xvf 'data.tar.xz' -C "${pkgdir}"
  rm -rf "${pkgdir}/usr/share/doc"
  install -dv "${pkgdir}/usr/bin"
  ln -sfv "/opt/Beekeeper Studio/beekeeper-studio" -t "${pkgdir}/usr/bin"
  install -Dvm644 "${pkgdir}/opt/Beekeeper Studio/"{'LICENSE.electron.txt','LICENSES.chromium.html'} \
    -t "${pkgdir}/usr/share/licenses/beekeeper-studio"
  install -Dvm644 "beekeeper-studio-${pkgver}-license" "${pkgdir}/usr/share/licenses/beekeeper-studio/LICENSE"
}
