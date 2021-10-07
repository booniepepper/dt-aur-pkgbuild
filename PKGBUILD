# This is an example PKGBUILD file. Use this as a start to creating your own,
# and remove these comments. For more information, see 'man PKGBUILD'.
# NOTE: Please fill out the license field for your package! If it is unknown,
# then please put 'unknown'.

# Maintainer: Gaoyang Zhang <gy@blurgy.xyz>
pkgname=dt
pkgver=0.1.0
pkgrel=1
epoch=
pkgdesc="Syncing dotfiles and more"
arch=("any")
url="https://github.com/blurgyy/dt"
license=('MIT OR Apache 2.0')
groups=()
depends=(cargo)
makedepends=(
    curl
    rustup
)
checkdepends=()
optdepends=()
provides=("dt-cli")
conflicts=("dt-git" "dt-bin")
replaces=()
backup=()
options=()
install=
changelog=
source=("https://github.com/blurgyy/dt/archive/refs/tags/v${pkgver}.tar.gz")
sha256sums=("9b4cea5f092194793a624ebc3ece43f84fb0daaeba0b7e9200b9982e32679f81")
noextract=()
validpgpkeys=()

build() {
    cd "$pkgname-$pkgver"
    cargo build --bin=dt-cli --release --all-features
}

check() {
    cd "$pkgname-$pkgver"
    cargo test --release --all-features
}

package() {
    cd "$pkgname-$pkgver"
    install -Dm755 "target/release/dt-cli" "$pkgdir/usr/bin/dt-cli"
    install -Dm644 "LICENSE" "$pkgdir/usr/share/licenses/dt/LICENSE"
}