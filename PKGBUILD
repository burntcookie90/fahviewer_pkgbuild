pkgname=fahviewer
pkgver=7.2.9
pkgrel=1
pkgdesc='This is the new and fully functional work unit viewer. FAHViewer (FVR) is modeled after the very popular PS3 viewer, and continues the many rendering options, ball and stick, space fill, zoom, rotation, etc., and adds snapshot capture and cycling to show folding in action.'
url="http://folding.stanford.edu/English/HomePage"
arch=('i686 x86_64')
license=('GPL3')
depends=('gtk2' 'python2' 'pygtk' 'glib' 'pango')
options=('!docs' '!libtool')
source=(https://fah-web.stanford.edu/file-releases/beta/release/fahviewer/debian-testing-64bit/v7.2/fahviewer_7.2.9_amd64.deb)
md5sums=('8b6c9060ec5a765e5b5cb7a04d78e345')

# Moronic server
DLAGENTS=("https::/usr/bin/curl -k -o %o %u")

package() {
  cd ${srcdir}
  tar -xf data.tar.gz

# python2 fixes  
  cd ${srcdir}/usr/bin/
  for _file in $(find . -name 'FAHViewer' -print); do
    sed -i 's_^#!.*/usr/bin/python_#!/usr/bin/python2_' "${_file}"
    sed -i 's_^#!.*/usr/bin/env.*python_#!/usr/bin/env python2_' "${_file}"
   done

  cd ${srcdir}
  install -D -m0755 ${srcdir}/usr/bin/FAHViewer ${pkgdir}/usr/bin/FAHViewer
  install -D -m0644 ${srcdir}/usr/share/pixmaps/FAHViewer*.png ${pkgdir}/usr/share/pixmaps/FAHViewer.png
  install -D -m0644 ${srcdir}/usr/share/applications/FAHViewer.desktop ${pkgdir}/usr/share/applications/FAHViewer.desktop
}

# vim:set ts=2 sw=2 et:
