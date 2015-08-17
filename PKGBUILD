# Contributor: Sebastian Wiesner <lunaryorn googlemail com>
# Maintainer: Stefan Husmann <stefan-husmann@t-online.de>
pkgname=python2-lodgeitlib
pkgver=0.6
pkgrel=4
pkgdesc="Command line script and client library for pocoo pastebin"
arch=('any')
url='http://packages.python.org/lodgeitlib'
license=('custom:MIT')
depends=('python2-distribute' 'python2-pygments' 'python2-configobj')
source=("http://pypi.python.org/packages/source/l/lodgeitlib/lodgeitlib-$pkgver.tar.gz")
md5sums=('dd8934865e70725ffb0808c450aaaf8b')

package() {
  cd "$srcdir/lodgeitlib-$pkgver"
  sed -i '1s+python+python2+' \
    $srcdir/lodgeitlib-$pkgver/lodgeitclient.py
  # pocoo died, changing default to paste.pound-python.org
  sed -i s+paste.pocoo.org+paste.pound-python.org+ *.py
  python2 setup.py install --root="$pkgdir" -O1
  install -Dm644 COPYING "$pkgdir/usr/share/licenses/$pkgname/COPYING"
}
