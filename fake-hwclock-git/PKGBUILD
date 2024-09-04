# Contributor: graysky <graysky AT archlinux DOT us>
# Contributor: David Manouchehri <manouchehri@riseup.net>

pkgname='fake-hwclock-git'
pkgver=0.1b.r21.g5b8105b
pkgrel=1
pkgdesc="Save/restore system clock on machines without working RTC hardware."
arch=('x86_64')
url="https://github.com/xanmanning/alarm-fake-hwclock"
license=('LicenseRef-Coffeeware')
depends=('glibc')
makedepends=('git')
conflicts=('fake-hwclock')
source=("$pkgname::git+${url}.git")
sha512sums=('SKIP')

pkgver() {
  cd "$pkgname"
  git describe --long | sed 's/^v//;s/\([^-]*-g\)/r\1/;s/-/./g'
}

build() {
  make -C "$pkgname"
}

package() {
  make -C "$pkgname" DESTDIR="${pkgdir}" install
  install -Dm644 "$pkgname/LICENSE" -t "$pkgdir/usr/share/licenses/$pkgname"
}
