# Maintainer: Knut Ahlers <knut@ahlers.me>
# Contributor: Sitansh Rajput <me [at] lostpolaris [dot] com>
# Contributor: Caltlgin Stsodaat <contact@fossdaily.xyz>
# Contributor: Michael Lutonsky <m@luto.at>
# Contributor: Tássio Virgínio <tassiovirginio@gmail.com>

pkgname='beekeeper-studio-bin'
pkgver=4.6.2
pkgrel=1
pkgdesc='Modern and easy to use SQL client for MySQL, Postgres, SQLite, SQL Server, and more'
arch=('x86_64')
url='https://www.beekeeperstudio.io'
license=('MIT')
depends=('libappindicator-gtk3' 'libnotify' 'libsecret' 'libxss' 'libxslt' 'nodejs' 'nss' 'xdg-utils')
provides=(beekeeper-studio)
conflicts=(beekeeper-studio)
source=("beekeeper-studio-${pkgver}-license::https://github.com/beekeeper-studio/beekeeper-studio/raw/v${pkgver}/LICENSE.md"
        "https://github.com/beekeeper-studio/beekeeper-studio/releases/download/v${pkgver}/beekeeper-studio_${pkgver}_amd64.deb")
sha256sums=('1409fbbc5265c85da91684660c87f85d74c3fdc63a2d355169f40dac5cc7a078'
            'b4f9f18db99f77c78628406efd15a057ec36a7a55867d6a3d02d00bcfbbb9ec5')

package() {
  tar -xvf 'data.tar.xz' -C "${pkgdir}"
  rm -rf "${pkgdir}/usr/share/doc"
  install -dv "${pkgdir}/usr/bin"
  ln -sfv "/opt/Beekeeper Studio/beekeeper-studio" -t "${pkgdir}/usr/bin"
  install -Dvm644 "${pkgdir}/opt/Beekeeper Studio/"{'LICENSE.electron.txt','LICENSES.chromium.html'} \
    -t "${pkgdir}/usr/share/licenses/beekeeper-studio"
  install -Dvm644 "beekeeper-studio-${pkgver}-license" "${pkgdir}/usr/share/licenses/beekeeper-studio/LICENSE"
}
