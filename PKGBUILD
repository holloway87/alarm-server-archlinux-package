# Maintainer: Holloway <me@holloway-web.de>
pkgname=hw-alarm-server
pkgver=1.0.1
pkgrel=1
pkgdesc='Server script for alarms.'
arch=('any')
url='https://github.com/holloway87/alarm-server'
license=('custom:WTFPL')
depends=('alsa-lib'
	'python'
	'python-websockets'
	'python-simpleaudio')
source=("https://github.com/holloway87/alarm-server/archive/refs/tags/v$pkgver.tar.gz"
	'alarm-server.service')
md5sums=('31b9f4249c0f92c288ee29c097023db6'
    '115f546f7d6e2469ab64a29c7077b0aa')

package()
{
    cd "alarm-server-$pkgver"
    for file in $(find . -type d); do echo $file; install -Ddm755 $file "$pkgdir/usr/share/hw-alarm-server/$file"; done
    for file in $(find . -type f); do echo $file; install -Dm644 $file "$pkgdir/usr/share/hw-alarm-server/$file"; done

    install -Dm644 ../alarm-server.service "$pkgdir/usr/lib/systemd/system/alarm-server.service"
}
