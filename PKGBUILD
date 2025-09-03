pkgname=libbpf
pkgver=1.5.1
pkgrel=1
pkgdesc="Library for loading eBPF programs and reading and manipulating eBPF objects from user-space"
arch=('x86_64')
url="https://github.com/libbpf/libbpf"
license=(
    'LGPL-2.1-only'
    'BSD-2-Clause'
)
depends=(
    'glibc'
    'libelf'
    'linux-api-headers'
    'zlib'
)
source=(https://github.com/libbpf/libbpf/archive/v${pkgver}/${pkgname}-${pkgver}.tar.gz)
sha256sums=(e5ff89750e48ab5ecdfc02a759aa0dacd1e7980e98e16bdb4bfa8ff0b3b4b98f)

build() {
    cd ${pkgname}-${pkgver}/src

    make CC="${CHOST}-gcc"
}

package() {
    cd ${pkgname}-${pkgver}/src

    make DESTDIR=${pkgdir} LIBSUBDIR=lib64 install
}
