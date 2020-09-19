# This is an example PKGBUILD file. Use this as a start to creating your own,
# and remove these comments. For more information, see 'man PKGBUILD'.
# NOTE: Please fill out the license field for your package! If it is unknown,
# then please put 'unknown'.

# Maintainer: Your Name <youremail@domain.com>
pkgname=gf_backup_tool
pkgver=0.2.1
pkgrel=1
pkgdesc="Terminal tool for backup based on rsync & systemd"
arch=('x86_64')
url="https://github.com/Gregory-F/gf_backup_tool"
license=('GPL')
depends=('systemd'
	'dateutils'
	'rsync'
	'bash'
	'sudo'
)
makedepends=('git')
checkdepends=()
backup=()
source=("git+$url")
        
noextract=()
md5sums=('SKIP')
validpgpkeys=()

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
    	cd "$pkgdir"
	sudo mkdir "/etc/gf_backup_tool"
	for var in {Custom,Hourly,Dailly,Weekly,Mounthly}
	do
	    sudo mkdir -p /snapshots/$var
	    done
	sudo cp "$srcdir/$pkgname/config" "/etc/gf_backup_tool/config" 
	sudo cp "$srcdir/$pkgname/exclude_file" "/etc/gf_backup_tool/exclude_file"
	sudo cp "$srcdir/$pkgname/backup_tool" "/usr/bin/backup_tool"
	sudo chmod +x "/usr/bin/backup_tool"
	#make DESTDIR="$pkgdir/" install
}

