# Maintainer: Piotr Miller <nwg.piotr@gmail.com>
pkgname=('rof-git')
pkgver=0.0.1
pkgrel=2
pkgdesc="Script to launch the command given as an argument if not yet running, else set focus to appropriate window"
arch=('x86_64')
url="https://github.com/nwg-piotr/tint2-executors"
license=('GPL3')
depends=('xorg-xprop' 'wmctrl')
source=("https://raw.githubusercontent.com/nwg-piotr/rof/master/rof")

md5sums=('6b970b4dc0c407d1e50a827873605178')

package() {
  install -D -m 755 rof \
 	 "$pkgdir"/usr/bin/rof
}