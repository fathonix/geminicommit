# Maintainer: Taufik Hidayat <tfkhdyt@proton.me>
pkgname=geminicommit-bin
pkgver=0.0.1
pkgrel=2
pkgdesc='A CLI that writes your git commit messages for you with Google Gemini AI'
arch=('x86_64')
url='https://github.com/tfkhdyt/geminicommit'
license=('GPL3')
depends=('git')
source=("${pkgname}-v${pkgver}.tar.gz::${url}/releases/download/v${pkgver}/geminicommit-v${pkgver}-linux-amd64.tar.gz")
md5sums=('ed00a68f72a6bc0aff855921da919650')

build() {
	./geminicommit completion bash > geminicommit.bash
	./geminicommit completion zsh > _geminicommit.zsh
	./geminicommit completion fish > geminicommit.fish
}

package() {
	install -Dm755 geminicommit "${pkgdir}/usr/bin/geminicommit"
	install -Dm644 geminicommit.bash "${pkgdir}/usr/share/bash-completion/completions/geminicommit"
	install -Dm644 _geminicommit.zsh "${pkgdir}/usr/share/zsh/site-functions/_geminicommit"
	install -Dm644 geminicommit.fish "${pkgdir}/usr/share/fish/vendor_completions.d/geminicommit.fish"
}
