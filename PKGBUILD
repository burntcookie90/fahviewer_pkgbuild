pkgname=fahviewer
pkgver=7.3.4
pkgrel=1
pkgdesc='Viewer for Folding@Home'
url="http://folding.stanford.edu/English/HomePage"
arch=('i686' 'x86_64')
license=('GPL3')
depends=('gtk2' 'glib' 'pango')
options=('!docs' '!libtool')

if test "$CARCH" == i686; then
  source=(https://fah-web.stanford.edu/file-releases/beta/release/fahviewer/debian-testing-32bit/v7.3/fahviewer_${pkgver}_i386.deb)
else
  source=(https://fah-web.stanford.edu/file-releases/beta/release/fahviewer/debian-testing-64bit/v7.3/fahviewer_${pkgver}_amd64.deb)
fi

md5sums=('97d6bc7a1a1f350518f4e443370456ed')

# Moronic server
DLAGENTS=("https::/usr/bin/curl -k -o %o %u")

package() {
  cd ${srcdir}
  tar -xf data.tar.gz

  cd ${srcdir}
  install -D -m0755 ${srcdir}/usr/bin/FAHViewer ${pkgdir}/usr/bin/FAHViewer
  install -D -m0644 ${srcdir}/usr/share/pixmaps/FAHViewer*.png ${pkgdir}/usr/share/pixmaps/FAHViewer.png
  install -D -m0644 ${srcdir}/usr/share/applications/FAHViewer.desktop ${pkgdir}/usr/share/applications/FAHViewer.desktop
}

# vim:set ts=2 sw=2 et:
