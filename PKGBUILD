pkgname=realvnc-viewer
pkgver=6.0.1
pkgrel=1
pkgdesc='VNC remote desktop viewer from RealVNC'
arch=('x86_64')
url='https://www.realvnc.com/'
license=('custom')
depends=(
    'libsm'
    'libice'
    'libx11'
    'libxext'
    'glibc'
    'gcc-libs'
    'util-linux'
    'libxcb'
    'libxau'
    'libxdmcp'
)
source=(
    "https://www.realvnc.com/download/file/viewer.files/VNC-Viewer-${pkgver}-Linux-x64.gz"
    'realvnc.desktop'
    'realvnc.png'
    'LICENSE'
)
md5sums=(
    '64d9497e2439687b791700ec09460d4f'
    'aaaf0206fd2506594fa399ca1f7fc38d'
    'c3dee43d3158eb5b0ccc5ab6d295dda6'
    '3d4ab7000b55918b1c2e30c42d317ad9'
)
options=(!strip)

package() {
    cd "${srcdir}"
    if [ ! -e ./realvnc ]; then
        ln -s ./VNC-Viewer-6.0.1-Linux-x64 ./realvnc
    fi
    install -Dm755 "${srcdir}/VNC-Viewer-6.0.1-Linux-x64" "${pkgdir}/usr/bin/VNC-Viewer-6.0.1-Linux-x64"
    install -Dm755 "${srcdir}/realvnc" "${pkgdir}/usr/bin/realvnc"
    install -Dm644 "${srcdir}/realvnc.desktop" "${pkgdir}/usr/share/applications/realvnc.desktop"
    install -Dm644 "${srcdir}/realvnc.png" "${pkgdir}/usr/share/icons/hicolor/48x48/apps/realvnc.png"
    install -Dm644 "${srcdir}/LICENSE" "${pkgdir}/usr/share/licenses/realvnc/LICENSE"
}
