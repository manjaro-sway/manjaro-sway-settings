# Maintainer: Jonas Strassel <info@jonas-strassel.de>

pkgname=manjaro-sway-settings
pkgver=3.2.1
pkgrel=5
arch=('any')
_pkgbase=desktop-settings
url="https://github.com/Manjaro-Sway/$_pkgbase/"
license=('GPL')
pkgdesc='Manjaro Sway Settings'
groups=('sway-manjaro')
depends=(
    'manjaro-base-skel'
    'waybar' # configurable bar
    'light' # cli to control brightness
    'mako' # desktop notifications
    'sway' # the desktop manager
    'sbdp' # sway config docs parser
    'wofi' # launcher application
    'swaylock' # lockscreen
    'grim' # screenshot tool
    'slurp' # helper for grim
    'wob' # wayland overlay bar for brightness and volume
    'termite' # configurable terminal application
    'wlogout' # nice logout menu
    'noto-fonts-emoji' # emji font
    'nerd-fonts-roboto-mono' # default monospace font
    'ttf-material-design-icons-webfont' # material design icons used in waybar
    'python-hjson' # cleaning json in config files
    'jq' # parsing and manipulating json
    'khal' # calendar application around caldav
    'lm_sensors' # display sensor information
    'mesa-demos' # required for terminal.sh script
    'manjaro-sway-wallpapers' # manjaro sway themed backgrounds
)
makedepends=('git')
optdepends=(
    'ranger: a keyboard centric file manager'
    'qutebrowser: a keyboard-centric browser'
    'flashfocus: better flashing on focus changes'
    'swaylock-effects: swaylock with nicer effects'
    'wlsunset: time & place based light temperature'
    'kanshi: automatically load matching output profiles'
    'autotiling: automated tiling'
    'kitty: terminal application with hardware acceleration'
)
conflicts=('manjaro-desktop-settings' 'manjaro-sway-settings-git')
provides=('manjaro-desktop-settings')
source=("$pkgname-$pkgver.tar.gz::${url}/archive/${pkgver}.tar.gz")
_sourcemd5=5e876865bda9624cdec24c4c4721eb2a
md5sums=("$_sourcemd5")

package() {
    install -d $pkgdir/etc
    install -d $pkgdir/usr
    cp -r $_pkgbase-$pkgver/community/sway/etc/* "${pkgdir}/etc/"
    cp -r $_pkgbase-$pkgver/community/sway/usr/* "${pkgdir}/usr/" 
}
