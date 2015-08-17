# Maintainer: Maxwell Pray a.k.a. Synthead <synthead@gmail.com>

pkgname=ruby1.8-kgio
pkgver=2.7.2
pkgrel=1
pkgdesc="Provides non-blocking I/O methods for Ruby without raising exceptions on EAGAIN and EINPROGRESS"
arch=('i686' 'x86_64')
url="http://bogomips.org/kgio/"
license=("GPL")
depends=('ruby1.8' 'rubygems1.8')
source=("http://gems.rubyforge.org/gems/${pkgname#ruby1.8-}-$pkgver.gem")
noextract=("${pkgname#ruby1.8-}-$pkgver.gem")
md5sums=('0690eef36ec7dc669e63290a2c3702cd')

package() {
	local _gemdir="$(ruby-1.8 -rubygems -e'puts Gem.default_dir')"
	gem-1.8 install -Vl --no-user-install --ignore-dependencies -i "$pkgdir$_gemdir" "$srcdir/${pkgname#ruby1.8-}-$pkgver.gem"
	sed -i "s/${pkgdir//\//\/}//" "$pkgdir$_gemdir/gems/${pkgname#ruby1.8-}-$pkgver/ext/${pkgname#ruby1.8-}/Makefile"
}
