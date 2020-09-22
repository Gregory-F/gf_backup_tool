# This is an example PKGBUILD file. Use this as a start to creating your own,
# and remove these comments. For more information, see 'man PKGBUILD'.
# NOTE: Please fill out the license field for your package! If it is unknown,
# then please put 'unknown'.

# Maintainer: Your Name <youremail@domain.com>
pkgname=gf_backup_tool
pkgver=0.8.r36.5cc679d
pkgrel=1
pkgdesc="Backup Terminal tool based on rsync & systemd"
arch=('x86_64')
url="https://github.com/Gregory-F/gf_backup_tool"
license=('GPL')
depends=('systemd'
	'dateutils'
	'rsync'
	'bash'
	'sudo'
)
install=gf_backup_tool.install
makedepends=(git sudo)
checkdepends=()
backup=()
source=("git+$url")
noextract=()
md5sums=('SKIP')
validpgpkeys=()

pkgver() {
  cd "${_pkgname}"
  git describe --long --tags | sed 's/\([^-]*-g\)/r\1/;s/-/./g'
}


#prepare() {
#	cd "$pkgname"
#}

#build() {
#	cd "$pkgname"
#	./configure --prefix=/usr
#	make
#}

#check() {
#	cd "$pkgname-$pkgver"
#	make -k check
#}

package() {
	for var in {Custom,Hourly,Dailly,Weekly,Mounthly}
	do
	    mkdir -p $pkgdir/snapshots/$var
        done
	#make PREFIX=/usr DESTDIR="$pkgdir/" install
	install -Dm 644 "$srcdir/$pkgname/config" "$pkgdir/etc/gf_backup_tool/config" 
	install -Dm 644 "$srcdir/$pkgname/exclude_file" "$pkgdir/etc/gf_backup_tool/exclude_file"
	install -Dm 645 "$srcdir/$pkgname/backup_tool" "$pkgdir/usr/bin/backup_tool"
	install -Dm 644 "$srcdir/$pkgname/gf_backup_tool.timer" "$pkgdir/etc/systemd/system/gf_backup_tool.timer"
	install -Dm 644 "$srcdir/$pkgname/gf_backup_tool.service" "$pkgdir/etc/systemd/system/gf_backup_tool.service"

}

