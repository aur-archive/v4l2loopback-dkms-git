# Maintainer: maz-1 < loveayawaka at gmail dot com> 

_pkgname=v4l2loopback
pkgname=${_pkgname}-dkms-git
_pkgver=0.8.0
pkgver=0.8.0.316.21195cd
pkgrel=1
pkgdesc="a kernel module to create V4L2 loopback devices"
arch=('any')
url="https://github.com/umlaeute/v4l2loopback"
license=('GPL')
depends=('dkms')
makedepends=('git')
provides=('v4l2loopback' 'v4l2loopback-dkms')
conflicts=('v4l2loopback' 'v4l2loopback-dkms')
install=install
source=("git+https://github.com/umlaeute/v4l2loopback.git"
        "dkms.conf")
md5sums=('SKIP'
	 '27ca945cebe8d62fe0c93c1fd6794ecf')

pkgver() {
  cd ${_pkgname}
  echo ${_pkgver}.$(git rev-list --count master).$(git rev-parse --short master)
}

build() {
	cd "$srcdir/${_pkgname}"
	rm -rf ./.git
	rm -rf ./dkms.conf
}

package() {
	cd "$srcdir/${_pkgname}"
	mkdir -p ${pkgdir}/usr/src
	cp -RL $srcdir/${_pkgname}  ${pkgdir}/usr/src/${_pkgname}-${_pkgver}
	rm -rf ${pkgdir}/usr/src/${_pkgname}-${_pkgver}/.git
	rm -rf ${pkgdir}/usr/src/${_pkgname}-${_pkgver}/dkms.conf
	cp $srcdir/dkms.conf ${pkgdir}/usr/src/${_pkgname}-${_pkgver}
	
}
