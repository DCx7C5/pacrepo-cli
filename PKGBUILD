# Maintainer: DCx7C5
pkgname=pacrepo-cli
pkgver=1.1.0.r0.g5b38d04
pkgrel=1
pkgdesc="Quick Tool for managing user repos in pacman.conf"
arch=('any')
url="https://github.com/dcx7c5/pacrepo-cli"
license=('ISC')
depends=(
  'python'
)
makedepends=(
  'git'
	'python-build'
	'python-installer'
	'python-wheel'
  'python-setuptools'
)
_name=${pkgname#python-}
source=(cli.py setup.py README.md)
sha256sums=(SKIP SKIP SKIP)

pkgver() {
    git describe --tags --long | sed 's/^v//;s/\([^-]*-g\)/r\1/;s/-/./g'
}

build() {
    python -m build --wheel --no-isolation
}

package() {
    python -m installer --destdir="$pkgdir" dist/*.whl
}
