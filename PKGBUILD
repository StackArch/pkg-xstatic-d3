# Maintainer: BigfootACA <bigfoot@classfun.cn>

_pyname=xstatic-d3
_pycname=XStatic-D3
pkgbase=python-$_pyname
pkgname=(python{,2}-$_pyname)
pkgver=3.5.17.0
pkgrel=1
pkgdesc="D3 3.5.17 (XStatic packaging standard)"
arch=(any)
url="http://d3js.org/"
license=(BSD)
makedepends=(
	python
	python-xstatic
	python-setuptools
	python2
	python2-xstatic
	python2-setuptools
)
source=(https://pypi.io/packages/source/${_pycname::1}/$_pycname/$_pycname-$pkgver.tar.gz)
md5sums=('2729f32f218b122999c26daeaf67a0a8')
sha256sums=('176e93eee7192e07fc54334ddb1a6b64fcfc8cde6abb23f65727856bb9dd1829')
sha512sums=('5b880c84017acbfa5a7e3e8052adf6b4793698ff31e5ded01afd9503df789a4705f01731a1122a5ff584dd3b7e3252cb1a609875dda324639eefaa9561d98b9a')

prepare(){
	sed -i '1s/from xstatic.pkg //g' $_pycname-$pkgver/setup.py
	cp -a $_pycname-$pkgver{,-py2}
}

_package_python(){
	depends=(
		python
		python-xstatic
	)
	cd $_pycname-$pkgver
	export PYTHONPATH=${PWD}/xstatic/pkg
	python setup.py install --root "$pkgdir" --optimize=1
}

_package_python2(){
	depends=(
		python2
		python2-xstatic
	)
	cd $_pycname-$pkgver-py2
	export PYTHONPATH=${PWD}/xstatic/pkg
	python2 setup.py install --root "$pkgdir" --optimize=1
}

eval "package_python-${_pyname}(){ _package_python; }"
eval "package_python2-${_pyname}(){ _package_python2; }"
