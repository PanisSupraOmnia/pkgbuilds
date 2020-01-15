#!/hint/bash -e
# Maintainer: Adrien Smith <adrien[at]bouldersmiths[dot]com>
# Contributor: Timothy Redaelli <timothy.redaelli@gmail.com>
# Contributor: DrZaius <lou[at]fakeoutdoorsman[dot]com>
# Contributor: gueek <cyttam[at]gmail[dot]com>

pkgname=pngout
pkgver=20200115
pkgrel=1
pkgdesc="Lossless PNG compressor"
arch=('i686' 'x86_64')
url="https://www.jonof.id.au/kenutils"
license=('custom')
depends=('glibc')
source=("https://www.jonof.id.au/files/kenutils/pngout-20200115-linux.tar.gz"
        'pngout.completion'
        'LICENSE')
sha512sums=('68b5878ca21ffba331e5a2a0e4f4ef54e3f2c2b82e38593761c9bb944518f450ce214203b95521965d5c81a904d8805d4c177f48e9bba0c3fd5833b265158b1c'
            '0401518413a4f2dbfe648e5f5e5c14f472223f4612ce57bacaabfd8077f8bd08b5ebec25d59e5868807c5004829cd1cc7e782e5f945c8c4959ce13eafb44c8de'
            '0ca45cfd8c5963948cae63ab79339d7f33a1be4585fb8b94c8773771f4b33d6a6f3e854dd3abd68b0c13eec013d98d6406cd81af08a357265ee64c93dc203896')
b2sums=('c1d74b0334f6e8cb75c53a0cc92a765d6a8d641aa777235ecb8b6e7e1928878c7007c111f0f41580363cb3dbe12e648528aa96e289112224410ed235b3ec7c81'
        '1c1655ec7dce9c88f554c259460558e8fb01e6d8f0646e4f67b7f24e0278722233ca2ff640f159beca0e6e734e3ab9ad79820911ce0b4f81861dfe62bb47723c'
        '215a4a129e67f7a9e5ff35f7410b6d04619782bcc20c12be36362ad786e19ed970bb6b57c96ea70b78a94900055ec582b9be7e31e541e48d96146e03cb60e2d7')

prepare() {
  mv "$pkgname-$pkgver-linux/amd64" "$pkgname-$pkgver-linux/x86_64"
}

package() {
  install -Dm755 "$pkgname-$pkgver-linux/${CARCH}/pngout" \
                 "${pkgdir}/usr/bin/pngout"
  install -Dm644 "pngout.completion" "${pkgdir}/etc/bash_completion.d/pngout"
  install -Dm644 "LICENSE" "${pkgdir}/usr/share/licenses/$pkgname/LICENSE"
}
