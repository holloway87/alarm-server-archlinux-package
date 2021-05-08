# Maintainer: Holloway <me@holloway-web.de>
pkgname=hw-alarm-server
pkgver=1.1.0
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
md5sums=('e7529c549d39dac26c44267363431a47'
    '115f546f7d6e2469ab64a29c7077b0aa')

package()
{
    cd "alarm-server-$pkgver"
    for file in $(find . -type d); do echo $file; install -Ddm755 $file "$pkgdir/usr/share/hw-alarm-server/$file"; done
    for file in $(find . -type f); do echo $file; install -Dm644 $file "$pkgdir/usr/share/hw-alarm-server/$file"; done

    install -Dm644 ../alarm-server.service "$pkgdir/usr/lib/systemd/system/alarm-server.service"
}
