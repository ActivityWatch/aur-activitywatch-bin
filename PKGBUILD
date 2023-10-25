# Maintainer: Erik Bjäreholt <erik@bjareho.lt>
# Maintainer: Johan Bjäreholt <johan@bjareho.lt>

# PRs welcome at: https://github.com/ActivityWatch/aur-activitywatch-bin

pkgname=activitywatch-bin
pkgver='0.12.3b12'
pkgrel=2
epoch=
pkgdesc="Log what you do on your computer. Simple, extensible, no third parties."
arch=('x86_64')
url="https://github.com/ActivityWatch/activitywatch"
license=('MPL2')
provides=("activitywatch")
conflicts=("activitywatch")
depends=(
    #'qt6-base'
    #'qt6-svg'
    #'gtk3'
    #'openssl-1.0'
freetype2
libgcrypt
at-spi2-core
glibc
fontconfig
libxdamage
libbsd
pcre2
pango
libxrender
xcb-util
libxfixes
qt6-base
harfbuzz
libxinerama
libglvnd
xz
qt6-webengine
libxcursor
glib2
libdatrie
wayland
gcc-libs
pixman
libx11
bash
zlib
lz4
systemd-libs
libxi
bzip2
cairo
libxcomposite
openssl-1.1
sqlite
xcb-util-cursor
keyutils
libepoxy
util-linux-libs
qt6-svg
readline
dbus
libgpg-error
libxcb
gdk-pixbuf2
libxkbcommon
krb5
libxkbcommon-x11
qt6-wayland
libxrandr
gtk3
xcb-util-image
xcb-util-renderutil
xcb-util-wm
libxext
e2fsprogs
libpng
libdrm
xcb-util-keysyms
fribidi
libthai

)
source=("https://github.com/ActivityWatch/activitywatch/releases/download/v${pkgver}/activitywatch-v${pkgver}-linux-x86_64.zip")
md5sums=('74f605bf34f9f352261ca9a53cc32082')

package() {
    # Install into /opt/activitywatch
    install -d $pkgdir/opt
    cp -r activitywatch $pkgdir/opt

    # Symlink executables to /usr/bin
    install -d $pkgdir/usr/bin
    execnames=("aw-qt")
    for name in "${execnames[@]}"; do
        ln -s /opt/activitywatch/$name $pkgdir/usr/bin/$name
    done

    modulenames=("aw-server" "aw-server-rust" "aw-watcher-afk" "aw-watcher-window")
    for name in "${modulenames[@]}"; do
        ln -s /opt/activitywatch/$name/$name $pkgdir/usr/bin/$name
    done

    # Add .desktop file for autostart
    install -Dm644 activitywatch/aw-qt.desktop -t $pkgdir/etc/xdg/autostart

    # See: https://aur.archlinux.org/packages/activitywatch-bin/#comment-834170
    #rm $pkgdir/opt/activitywatch/libharfbuzz.so*
    #rm $pkgdir/opt/activitywatch/libfreetype.so*
    #rm $pkgdir/opt/activitywatch/libfontconfig.so*

    # These takes a lot of space, getting rid of them would be nice
    #rm $pkgdir/opt/activitywatch/libicu*.so*

    # One or more of these is making aw-qt SEGFAULT
    #rm $pkgdir/opt/activitywatch/libreadline.so*
    #rm $pkgdir/opt/activitywatch/libssl.so*
    #rm $pkgdir/opt/activitywatch/libavahi*.so*
    #rm $pkgdir/opt/activitywatch/libQt5*.so*
    #rm $pkgdir/opt/activitywatch/libstdc++.so*
    #rm $pkgdir/opt/activitywatch/libgpg-error.so*
    #rm $pkgdir/opt/activitywatch/libz.so*
    #rm $pkgdir/opt/activitywatch/libX*.so*
    #rm $pkgdir/opt/activitywatch/libxcb*.so*
    #rm $pkgdir/opt/activitywatch/libwayland*.so*
    #rm $pkgdir/opt/activitywatch/libpng*.so*
    #rm $pkgdir/opt/activitywatch/libgtk*.so*
    #rm $pkgdir/opt/activitywatch/libgnutls*.so*
    #rm $pkgdir/opt/activitywatch/libcairo*.so*
}
