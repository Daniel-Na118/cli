# Maintainer: Your Name <your email>

pkgname='creomnia-cli'
pkgver=1.0.6
pkgrel=1
pkgdesc='The main cli for the Creomnia dotfiles'
arch=('any')
license=('GPL-3.0-only')
depends=('python' 'python-pillow' 'python-materialyoucolor' 'libnotify' 'swappy' 'grim' 'dart-sass'
         'app2unit' 'wl-clipboard' 'slurp' 'gpu-screen-recorder' 'dconf' 'cliphist' 'fuzzel')
makedepends=('python-build' 'python-installer' 'python-hatch' 'python-hatch-vcs')
provides=('creomnia-cli')
conflicts=('caelestia-cli' 'caelestia-cli-git')

build() {
    # Building from the local directory
    cd "$startdir"
    python -m build --wheel --no-isolation
}

package() {
    cd "$startdir"
    
    # Install the wheel
    python -m installer --destdir="$pkgdir" dist/*.whl
    
    # Install fish completions
    install -Dm644 ./completions/creomnia.fish "$pkgdir"/usr/share/fish/vendor_completions.d/creomnia.fish
}
