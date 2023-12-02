# Maintainer: Jonas Strassel <info@jonas-strassel.de>

pkgname=manjaro-sway-settings
pkgver=16.2.0
pkgrel=0
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
    'sway'                    # window manager
    'rofi-wayland'            # launcher application
    'swaylock'                # lockscreen
    'swayidle'                # idle management daemon
    'swayr'                   # window switcher
    'grim'                    # screenshot tool
    'slurp'                   # helper for grim
    'wob'                     # wayland overlay bar for brightness and volume
    'foot'                    # terminal application
    'foot-terminfo'           # terminal info for foot
    'jq'                      # json parsing and manipulation
    'calcurse'                # tui calendar application
    'lm_sensors'              # display sensor information
    'wf-recorder'             # screen recording util
    'wl-clipboard'            # copy/paste utilities for wayland
    'nwg-wrapper'             # conky like onscreen information'
    'noto-fonts-emoji'        # emoji font (e.g. weather icons)
    'htop'                    # system monitor
    'swappy'                  # screenshot editing tool
    'inotify-tools'           # file watchers etc
    'bluetuith'               # bluetooth management tool
    'swayr'                   # lru window switcher for sway
    'bc'                      # basic tiny calculation util
    'xdg-terminal-exec-git'   # upcoming execute in terminal xdg standard
    ## theme
    'ttf-jetbrains-mono-nerd' # default monospace font
    'ttf-roboto'              # default font
    'papirus-maia-icon-theme' # default icon theme
    'xcursor-breeze'          # default cursor theme
    'matcha-gtk-theme'        # default gtk (gnome etc.) theme
    'kvantum-theme-matcha'    # default kvantum (kde etc.) theme
)
makedepends=('git')
optdepends=(
    'qutebrowser: a keyboard-centric browser'
    'flashfocus: better flashing on focus changes'
    'swaylock-effects: swaylock with nicer effects'
    'wlsunset: time & place based light temperature'
    'kanshi: automatically load matching output profiles'
    'autotiling-rs: automated tiling'
    'sworkstyle: dynamic workspace names (icons) in waybar'
    'nwg-wrapper: conky like onscreen information'
    'cliphist: clipboard manager'
    'swaycwd: open here helper'
    'zeit: a simple time tracker'
    'dex: execute DesktopEntry files on autostart'
    'poweralertd: battery and power notifications'
    'wluma: adaptive brightness based on screen contents and ALS'
)
conflicts=('manjaro-sway-settings-git')
provides=('manjaro-desktop-settings')
_sourcemd5=527eab4139e76734acf9f0adbeee7769
source=(
    "$pkgname-$pkgver.tar.gz::${url}/archive/${pkgver}.tar.gz"
    "https://github.com/arcolinux/arcolinux-on-the-road/raw/cfbcc902b9520cc4ff73584dd80f34c54a158c75/root/usr/local/bin/skel"
)
md5sums=(
    "$_sourcemd5"                      # desktop settings
    "3ce84d692c6fdbaf31e1b602bc890aa4" # skel update script from arcolinux
)
install=.install

package() {
    install -d "$pkgdir"/etc
    install -d "$pkgdir"/usr/bin
    cp -r $_pkgbase-$pkgver/community/sway/etc/* "${pkgdir}/etc/"
    cp -r $_pkgbase-$pkgver/community/sway/usr/* "${pkgdir}/usr/"
    install -D -m 755 skel "${pkgdir}/usr/bin/skel"
}
