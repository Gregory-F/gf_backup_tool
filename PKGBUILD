# This is an example PKGBUILD file. Use this as a start to creating your own,
# and remove these comments. For more information, see 'man PKGBUILD'.
# NOTE: Please fill out the license field for your package! If it is unknown,
# then please put 'unknown'.

# Maintainer: Your Name <youremail@domain.com>
pkgname=gf_backup_tool
pkgver=6.2.r15.e337237
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
makedepends=(git install sudo)
checkdepends=()
backup=()
source=("git+$url")
        
noextract=()
md5sums=('SKIP')
validpgpkeys=()

pkgver() {
  cd "${_pkgname}"
  printf "6.2.r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
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
	    sudo mkdir -p /snapshots/$var
        done
	#make PREFIX=/usr DESTDIR="$pkgdir/" install
	sudo install -Dm644 "$srcdir/$pkgname/config" "/etc/gf_backup_tool/config" 
	sudo install -Dm644 "$srcdir/$pkgname/exclude_file" "/etc/gf_backup_tool/exclude_file"
	sudo install -Dm645 "$srcdir/$pkgname/backup_tool" "/usr/bin/backup_tool"
}

