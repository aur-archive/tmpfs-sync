# Maintainer: trile7 at gmail dot com

pkgname=tmpfs-sync
pkgver=0.4.2
pkgrel=3
pkgdesc="Speed up data access and reduce read/write to SSD by move directories to tmpfs and sync them to physical disk on demand or when daemon stop"
url="http://bashscripts.googlecode.com"
arch=('i686' 'x86_64')
license=('GPL3')
depends=('bash' 'coreutils' 'rsync')
install=$pkgname.install
source=($url/files/$pkgname-$pkgver.tar.gz)

package() {
  cd "$srcdir/$pkgname-$pkgver"
  mkdir -p "$pkgdir/usr/share/$pkgname" "$pkgdir/usr/bin"
  cp * "$pkgdir/usr/share/$pkgname"
  ln -s "/usr/share/$pkgname/$pkgname" "$pkgdir/usr/bin/$pkgname"
  install -Dm755 $pkgname.rc "$pkgdir/etc/rc.d/$pkgname"
  install -Dm644 $pkgname.service "$pkgdir/usr/lib/systemd/system/$pkgname.service"
  install -Dm755 $pkgname.sync "$pkgdir/etc/cron.hourly/$pkgname.sync"
}

md5sums=('bcd3238b2267da64920e51a289941897')
