pkgname=libbpf
pkgver=1.6.2
pkgrel=2
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
sha256sums=(16f31349c70764cba8e0fad3725cc9f52f6cf952554326aa0229daaa21ef4fbd)

build() {
    cd ${pkgname}-${pkgver}/src

    make CC="${CHOST}-gcc"
}

package() {
    cd ${pkgname}-${pkgver}/src

    make DESTDIR=${pkgdir} LIBSUBDIR=lib64 install
}
