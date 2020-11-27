# Maintainer: LibreFreq <sorry@dontbugme.now>
# myversion: 0.00.003 alpha
pkgname=fsradio-git
_gitname=fsradio
pkgver=r21.cb1e9e1
pkgrel=0.3
pkgdesc='A POSIX shell script to controll a Frontier Silicon Wi-Fi radio via fsapi. Early alpha.'
arch=('any')
license=('MIT')
depends=('coreutils' 'curl' 'gawk' 'gvim' 'inetutils' 'procps-ng' 'sed' 'xmlstarlet' )
makedepends=('git')
optdepends=('libpulse' 'pulseaudio-dlna-python3-git: streaming live audio via dlna' 
            'pavucontrol: GTK3-GUI for PulseAudio' 'pavucontrol-qt: QT-GUI for PulseAudio' 'wget: spider the webpage' 
            'nmap: discover fsradios with MAC-prefix and forensic' 'sudo: to use nmap')
provides=('fsradio')
conflicts=('fsradio')
replaces=('fsradio')
url='https://github.com/LiberationFrequency/fsradio'
source=('git://github.com/LiberationFrequency/fsradio.git')
md5sums=('SKIP')

pkgver() {
	cd "${srcdir}/${_gitname}"
        ( set -o pipefail
        git describe --long 2>/dev/null | sed 's/\([^-]*-g\)/r\1/;s/-/./g' ||
        printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
        )
}

package() {
	cd "${srcdir}/${_gitname}"
	install -Dm755 ./fsradio "${pkgdir}/usr/bin/fsradio"
        install -Dm644 fscheckdep "${pkgdir}/usr/bin/fscheckdep"
        install -Dm644 dec2ipv4 "${pkgdir}/usr/bin/dec2ipv4"
        install -Dm644 ipv42dec "${pkgdir}/usr/bin/ipv42dec"
        install -Dm644 reversecounter "${pkgdir}/usr/bin/reversecounter"
        install -Dm644 README.md "${pkgdir}/usr/bin/share/fsdata/README.md"
        install -Dm644 share/fsdata/dependencies.json "${pkgdir}/usr/bin/share/fsdata/dependencies.json"
        install -Dm644 share/fsdata/dabCIdECCs.csv "${pkgdir}/usr/bin/share/fsdata/dabCIdECCs.csv"
        install -Dm644 share/fsdata/dabEIDs.csv "${pkgdir}/usr/bin/share/fsdata/dabEIDs.csv"
        install -Dm644 share/fsdata/dabSIDs.csv "${pkgdir}/usr/bin/share/fsdata/dabSIDs.csv"
        install -Dm644 share/fsdata/rdspi.csv "${pkgdir}/usr/bin/share/fsdata/rdspi.csv"
        install -Dm644 share/fsdata/xmldecode.sed "${pkgdir}/usr/bin/share/fsdata/xmldecode.sed"
        install -Dm644 share/fsdata/fstools/rdspi_csv2json "${pkgdir}/usr/bin/share/fsdata/fstools/rdspi_csv2json"
        install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${_gitname}/LICENSE"
}
