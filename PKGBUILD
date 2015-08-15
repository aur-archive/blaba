# Maintainer: Limao Luo <luolimao+AUR@gmail.com>

_pkgname=blaba
pkgname=$_pkgname
pkgver=13.05
pkgrel=1
pkgdesc="Bryan Lunduke's Awesome Blocks of Awesome: A graphical video game editor"
arch=(i686 x86_64)
url=http://lunduke.com/?page_id=3152
license=(custom:GLL)
depends=(desktop-file-utils gtk2)
[[ $CARCH == "x86_64" ]] && depends[1]=lib32-gtk2
install=$_pkgname.install
source=(http://www.lunduke.com/dl/gmi-13.05-linux32bit.tar.gz
    LICENSE
    $_pkgname.desktop
    $_pkgname.png)
sha256sums=('95fed8cb18e528e5368fc95c08d9d1e4e1a7678f5a9f9969078b4ea1b61d2433'
    '72f4a64010d31d601c2780344b52c87ce08d5c604e1d58255578cd9cc3c8fc5a'
    'c92701530c651a76c4ae346cf8f7d053649e330ef9d8a3ec9f8cdf41c9612dbc'
    'b89d0c18cfb6a116f2c95a2326c7ce9e42b7169d9361add5260534ad3ba7edcd')
sha512sums=('8bb831f18773b5822d3332e9a549cd0d0cd72e3bb4e10b53beb0c169c6725f56ee7f014d53c9fb1d19640a4cca506e359cd02254e48ad600d84c7eb2db167bfa'
    'beba5402b92dd9e756a1afd4b5d2cbcb8b70b110bb0db5b1ca2bc24a010f4ade92bfdca8ef548cfbc52a17b565010421bb793410366c4c41fd0127fc0d6dec90'
    '2d645b6834594c1645401760d8de41d68b35c33ff447ae370b94cbb085a610bbd445a107b55ed5d986523e159cb310b0bfc84121493c97b865288c585382d940'
    'ef0dc0d070dc6a0eb3c37052b4bda82b42aefb1950d64ea9685de44dc10762a35021f4f5993c92d0670d134f99d3c5bba662f6eebebd55bbd99c38a2893b0c4a')

package() {
    install -Dm644 LICENSE "$pkgdir"/usr/share/licenses/$pkgname/LICENSE
    install -Dm644 $_pkgname.png "$pkgdir"/usr/share/pixmaps/$_pkgname.png

    install -d "$pkgdir"/opt/
    cp -r $_pkgname/ "$pkgdir"/opt/$pkgname

    desktop-file-install $_pkgname.desktop --dir "$pkgdir"/usr/share/applications/

    install -d "$pkgdir"/usr/bin/
    ln -s /opt/$pkgname/$_pkgname "$pkgdir"/usr/bin/$_pkgname
}
