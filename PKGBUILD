# Maintainer: Nathan Yang <nryang@users.noreply.github.com>
# Based on https://aur.archlinux.org/packages/brother-hl-l8260cdw
pkgname="brother-mfc-l5850dw"
pkgver="3.5.1"
pkgrel=1
pkgdesc="LPR and CUPS driver for the Brother MFC-L5850DW"
arch=('i686' 'x86_64')
url="https://support.brother.com/g/b/producttop.aspx?c=us&lang=en&prod=mfcl5850dw_us"
license=('custom:brother commercial license')
depends=('cups' 'perl')
install='brother-mfc-l5850dw.install'
source=(
  "https://download.brother.com/welcome/dlf102624/mfcl5850dwcupswrapper-3.5.1-1.i386.rpm"
  "https://download.brother.com/welcome/dlf102623/mfcl5850dwlpr-3.5.1-1.i386.rpm"
  'cupswrapper-license.txt'
  'lpr-license.txt'
)
md5sums=('ff85f2f70b337151ad5e4e93b92cd3f7'
         '0f7f9b7624c0f39d0be6a5fbf745446f'
         '97ad0cffd216059e9d1d3121899d8646'
         '5e87a3dc0f3e3438c088eda0f3565f0d')
if test "$CARCH" == x86_64; then
  depends+=('lib32-glibc')
fi

package() {
  printer_model=MFCL5850DW
  ppd_file=/opt/brother/Printers/${printer_model}/cupswrapper/brother-${printer_model}-cups-en.ppd
  lpd_file=/opt/brother/Printers/${printer_model}/cupswrapper/lpdwrapper

  cp -R $srcdir/opt $pkgdir
  
  install -d $pkgdir/usr/share/ppd
  ln -s ${ppd_file} $pkgdir/usr/share/ppd/brother_${printer_model}_printer_en.ppd
  install -d $pkgdir/usr/share/cups/model
  ln -s ${ppd_file} $pkgdir/usr/share/cups/model/brother_${printer_model}_printer_en.ppd
  install -d $pkgdir/usr/lib/cups/filter
  ln -s ${lpd_file} $pkgdir/usr/lib/cups/filter/brother_lpdwrapper_${printer_model}

  install -m 644 -D cupswrapper-license.txt $pkgdir/usr/share/licenses/${pkgname}/cupswrapper-licence.txt
  install -m 644 -D lpr-license.txt $pkgdir/usr/share/licenses/${pkgname}/lpr-licence.txt
}
