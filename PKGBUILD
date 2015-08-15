# Maintainer: Guillaume Laville <laville.guillaume@gmail.com>

pkgname=gedit-classbrowser3g
pkgver=1.1
pkgrel=1
pkgdesc='This package is a fork of Class Browser Plugin. The default parser uses ctags to support a wide range of languages and special parsers for Python, HTML, XML/Mallard/DocBook, Diff, Ruby and Markdown.'

arch=('i686' 'x86_64')
provides=()
replaces=()
license=('GPL3')
url='https://launchpad.net/gedit-classbrowser3g'
depends=('gedit>=3' 'ctags' 'python')
options=('')
source=(https://launchpad.net/gedit-classbrowser3g/trunk/${pkgver}/+download/gedit-classbrowser3g-${pkgver}.tar.gz)
install='gedit-classbrowser3g.install'
backup=()

sha256sums=('e68193845709f62935692d888603bf0ee2e601197d66e1b3780374965cfca8cc')

build() {
  cd ${srcdir}/gedit-classbrowser3g-${pkgver} || return 1
  
  install -D -m644 classbrowser3g.plugin ${pkgdir}/usr/lib/gedit/plugins/classbrowser3g.plugin
  
  for i in `ls classbrowser3g/parsers/`; do 
	  install -D -m644 classbrowser3g/parsers/${i} ${pkgdir}/usr/lib/gedit/plugins/classbrowser3g/parsers/${i} || return 1
  done;
  
  for i in `ls classbrowser3g/pixmaps/`; do 
	  install -D -m644 classbrowser3g/pixmaps/${i} ${pkgdir}/usr/lib/gedit/plugins/classbrowser3g/pixmaps/${i} || return 1
  done;

  for i in `ls classbrowser3g | grep -v pixmap | grep -v parsers`; do 
	  install -D -m644 classbrowser3g/${i} ${pkgdir}/usr/lib/gedit/plugins/classbrowser3g/${i} || return 1
  done;
  
  install -D -m644 org.gnome.gedit.plugins.classbrowser3g.gschema.xml ${pkgdir}/usr/share/glib-2.0/schemas/org.gnome.gedit.plugins.classbrowser3g.gschema.xml

}
