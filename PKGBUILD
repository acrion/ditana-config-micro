# Maintainer: Stefan Zipproth <s.zipproth@ditana.org>

pkgname=ditana-config-micro
pkgver=1.05
pkgrel=1
pkgdesc="Ditana micro editor configuration, including a desktop file for XFCE"
arch=(any)
url="https://ditana.org"
license=('AGPL-3.0-or-later AND MIT AND GPL-2.0-only')
conflicts=()
depends=(micro xclip exo)
makedepends=()
source=(
    'settings.json'
    'ditana-set-micro-as-default-editor.sh'
    'micro.desktop'
    '10-ditana-micro'
)
sha256sums=(
    'SKIP'
    'SKIP'
    'SKIP'
    'SKIP'
)

package() {
    install -Dm644 $srcdir/settings.json $pkgdir/etc/skel/.config/micro/settings.json
    install -Dm644 $srcdir/ditana-set-micro-as-default-editor.sh $pkgdir/etc/profile.d/ditana-set-micro-as-default-editor.sh

    # we overrule the default desktop shortcut to use exo-open --launch TerminalEmulator micro %F
    install -Dm755 $srcdir/micro.desktop $pkgdir/etc/skel/.local/share/applications/micro.desktop

    # Install the custom sudoers configuration to preserve the EDITOR and VISUAL environment variables in the sudo context,
    # ensuring that 'micro' is used as the default editor even when elevated permissions are required.
    install -Dm440 $srcdir/10-ditana-micro $pkgdir/etc/sudoers.d/10-ditana-micro

    # Ensure the correct directory permissions for /etc/sudoers.d/ to avoid
    # warning: directory permissions differ on /etc/sudoers.d/
    # filesystem: 750  package: 755
    chmod 750 $pkgdir/etc/sudoers.d/
}
