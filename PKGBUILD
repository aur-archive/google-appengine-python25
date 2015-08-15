# Maintainer: pisuka <tekmon@gmail.com>
# Contributor: Estevao Valadao <estevao@archlinux-br.org>
# Contributor: Guten <ywzhaifei@gmail.com>
# Contributor: Lee.MaRS <leemars@gmail.com>

pkgname=google-appengine-python25
pkgver=1.6.1
pkgrel=1
arch=(any)
pkgdesc="Google App Engine SDK for Python."
url=http://code.google.com/appengine/
license=(APACHE)
depends=(python25-ssl)
optdepends=(python25-pil)
makedepends=(unzip)
conflicts=(google-appengine-python)
provides=(google-appengine-python)
options=(!strip)
install=install
source=(http://googleappengine.googlecode.com/files/google_appengine_${pkgver}.zip)
noextract=(google_appengine_${pkgver}.zip)
sha1sums=(e9882abe0381111cc52a210f5c59e3d24202b5d2)

build() {
  cd "$pkgdir"
  mkdir -p opt usr/bin

  # Extract with unzip as bsdtar screws up permissions
  unzip -q "$srcdir/google_appengine_${pkgver}.zip" -d opt

  grep -r -l python opt/google_appengine | xargs sed -i '/#!\/usr\/bin\/env python/s|python|python2\.5|'

  find opt/google_appengine -maxdepth 1 -type f -executable -printf "/opt/google_appengine/%f\n" | xargs ln -st usr/bin/
}

