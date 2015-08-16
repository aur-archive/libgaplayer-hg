# Maintainer: Sander Jansen <s.jansen@gmail.com>
pkgname=libgaplayer-hg
pkgver=217
pkgrel=1
pkgdesc="Audio Player Library"
arch=('i686' 'x86_64' 'arm')
url="http://code.google.com/p/gogglesmm/"
license=('GPL3')
provides=('libgaplayer')
depends=('fox-devel>=1.7.28' 'libogg' 'libvorbis' 'flac' 'libmad' 'faad2' 'libxml2')
makedepends=('mercurial' 'pkgconfig' 'libpulse' 'alsa-lib')
optdepends=('libpulse: PulseAudio Output' 'alsa-lib: Alsa Output')
md5sums=() #generate with 'makepkg -g'

_hgroot="http://code.google.com/p"
_hgrepo="gogglesmm.gap"

build() {
  msg "Starting build..."
  rm -rf "$srcdir/$_hgrepo-build"
  cp -r "$srcdir/$_hgrepo" "$srcdir/$_hgrepo-build"
  cd "$srcdir/$_hgrepo-build"

  # Disabled most of the features that are not finished or currently not used.
  ./configure --without-jack --without-rsound --without-cdda --without-samplerate --without-mms --without-smb --without-wavpack
  make
}

package() {
  cd "$srcdir/$_hgrepo-build"
  make DESTDIR="$pkgdir/" install
}

# vim:set ts=2 sw=2 et:
