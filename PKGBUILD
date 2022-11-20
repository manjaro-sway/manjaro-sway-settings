# Maintainer: Jonas Strassel <info@jonas-strassel.de>

pkgname=manjaro-sway-settings
pkgver=12.1.3
pkgrel=21
arch=('any')
_pkgbase=desktop-settings
url="https://github.com/Manjaro-Sway/$_pkgbase"
license=('GPL')
pkgdesc='Manjaro Sway Settings'
groups=('sway-manjaro')
depends=(
    'manjaro-base-skel'
    'waybar'                  # configurable bar
    'light'                   # cli to control brightness
    'mako'                    # desktop notifications
    'sway'                    # the desktop manager
    'rofi-wayland'            # launcher application
    'swaylock'                # lockscreen
    'swayidle'                # idle management daemon
    'grim'                    # screenshot tool
    'slurp'                   # helper for grim
    'wob'                     # wayland overlay bar for brightness and volume
    'foot'                    # terminal application
    'foot-terminfo'           # terminal info for foot
    'nerd-fonts-roboto-mono'  # default monospace font
    'jq'                      # json parsing and manipulation
    'khal'                    # calendar application around caldav
    'lm_sensors'              # display sensor information
    'manjaro-sway-wallpapers' # manjaro sway themed backgrounds
    'wf-recorder'             # screen recording util
    'wl-clipboard'            # copy/paste utilities for wayland
    'nwg-wrapper'             # conky like onscreen information'
    'noto-fonts-emoji'        # emoji font (e.g. weather icons)
    'swaybg'                  # background switcher
    'ttf-liberation'          # contains the roboto font used in a lot of places
    'htop'                    # system monitor
)
makedepends=('git')
optdepends=(
    'qutebrowser: a keyboard-centric browser'
    'flashfocus: better flashing on focus changes'
    'swaylock-effects: swaylock with nicer effects'
    'wlsunset: time & place based light temperature'
    'kanshi: automatically load matching output profiles'
    'autotiling: automated tiling'
    'sworkstyle: dynamic workspace names (icons) in waybar'
    'nwg-wrapper: conky like onscreen information'
    'cliphist: clipboard manager'
    'swaycwd: open here helper'
    'zeit: a simple time tracker'
    'dex: execute DesktopEntry files on autostart'
    'poweralertd: battery and power notifications'
)
conflicts=('manjaro-desktop-settings' 'manjaro-sway-settings-git')
provides=('manjaro-desktop-settings')
_sourcemd5=4ced704b4af38eca4bef98e078b7cbbd
source=(
    "$pkgname-$pkgver.tar.gz::${url}/archive/${pkgver}.tar.gz"
    "waybar-tooltips.tar.gz::https://github.com/TheChymera/waybar-tooltips/archive/0.0.4.tar.gz"
    "https://github.com/arcolinux/arcolinux-on-the-road/raw/cfbcc902b9520cc4ff73584dd80f34c54a158c75/root/usr/local/bin/skel"
)
md5sums=(
    "$_sourcemd5"                      # desktop settings
    "f900eaacb1824e05c37ac4fb4a62436d" # waybar tooltips
    "3ce84d692c6fdbaf31e1b602bc890aa4" # skel update script from arcolinux
)
install=.install

package() {
    install -d $pkgdir/etc
    install -d $pkgdir/usr/bin
    cp -r $_pkgbase-$pkgver/community/sway/etc/* "${pkgdir}/etc/"
    cp -r $_pkgbase-$pkgver/community/sway/usr/* "${pkgdir}/usr/"
    install -D waybar-tooltips-0.0.4/bin/waybar-tooltip-khal.py "${pkgdir}/usr/share/sway/scripts/khal.py"
    install -D waybar-tooltips-0.0.4/LICENSE "${pkgdir}/usr/share/sway/scripts/khal.py.LICENSE"
    install -D -m 755 skel "${pkgdir}/usr/bin/skel"
}
