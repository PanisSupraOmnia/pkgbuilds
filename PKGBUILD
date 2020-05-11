# Maintainer: Adrien Smith <adrien at bouldersmiths.com>
# Contributor: Alif <alive4ever at live dot com>

pkgname=tmux-bash-completion-git
pkgver=r16.f5d5323
pkgrel=1
pkgdesc="Bash completion for tmux"
arch=('any')
url="https://github.com/imomaliev/tmux-bash-completion"
license=('GPL2')
depends=('bash-completion' 'tmux')
makedepends=('git')
provides=("${pkgname%-git}")
conflicts=("${pkgname%-git}")
source=("git+$url")
md5sums=('SKIP')

pkgver() {
  cd "${pkgname%-git}"
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

package() {
  cd "${pkgname%-git}/completions"
  for file in * ; do
    install -Dm644 "$file" "$pkgdir/usr/share/bash-completion/completions/$file"
  done
}
