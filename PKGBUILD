# Maintainer: Jan Boelsche <jan@lagomorph.de>
pkgname='stefans-user'
pkgver=2.0
pkgrel=1
pkgdesc='Creates a user called "stefans" and installs some dotfiles and an ssh public key'
packager='Jan Boelsche'
arch=('any')
license=('GPL')
groups=()
depends=()
makedepends=()
checkdepends=()
optdepends=()
install=${pkgname}.install
source=(
  '.vimrc'
  '.tmux.conf'
  'authorized_keys'
  'stefans'
)

sha256sums=('a8668316913ad6a3aa28c814d1cc65c6215574bf22010cbbac2ae3470f52478d'
            '554807de544674eacbd7a56aad43296ff7ca4c0e56a5141436b81f9795fc73cf'
            'b55dea49e3393815f9e883dc870b271dbeb03f3e9682c7caf47c7b95a0dee7d0'
            '954ee494fada6a61510f3d8e7a0859e757abb4d5f205c9a08a95aff4f6bfba8a')

package() {
  home="${pkgdir}/home/stefans"
	install -m 700 -d "${home}"
	install -m 600 -t "${home}" .tmux.conf .vimrc
	install -m 700 -d "${home}/.ssh"
	install -m 644 -t "${home}/.ssh" authorized_keys
	
  install -Dm 644 -t "${pkgdir}/var/lib/AccountsService/users/" stefans
}
