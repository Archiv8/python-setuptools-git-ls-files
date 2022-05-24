#!/bin/bash

# Created from the original PKGBUILD by Caleb Maclennan <caleb@alerque.com>

# Disable various shellcheck rules that produce false positives in this file.
# Repository rules should be added to the .shellcheckrc file located in the
# repository root directory, see https://github.com/koalaman/shellcheck/wiki
# and https://archiv8.github.io for further information.
# shellcheck disable=SC2034,SC2154
# ToDo: Add files: User documentation
# ToDo: Add files: Tooling
# FixMe: Namcap warnings and errors

# Maintainer: Ross Clark <https://github.com/Archiv8/python-setuptools-git-ls-files/discussions>
# Contributor: Ross Clark <https://github.com/Archiv8/python-setuptools-git-ls-files/discussions>

_langname="python"
_relname="setuptools_git_ls_files"
_pacname="setuptools-git-ls-files"

pkgname="${_langname}-${_pacname}"
pkgver=0.1.2
pkgrel=2
pkgdesc="A plugin for setuptools that finds all git tracked files, including submodules"
arch=(
	"any"
	)
url="https://github.com/anthrotype/setuptools_git_ls_files"
license=(
	"MIT"
	)
depends=(
	"python"
	)
makedepends=(
	"python-setuptools-scm"
	)
_tarname="${_relname}-$pkgver"
source=(
	"https://files.pythonhosted.org/packages/source/${_relname::1}/$_relname/$_tarname.tar.gz"
	)
sha512sums=(
	"30bfc33e4b55d7992000094cd8644d0ed1b788ae9fde9167d50c4734c50b4ff2f6d50155e731237f13ac425034e0c443349a97f95be5863052e6e15c466276aa"
	)

build() {

	cd "$_tarname"

	python setup.py build
}

package() {
	cd "$_tarname"

	python setup.py install --root="$pkgdir" --optimize=1 --skip-build

	install -Dm0644 -t "$pkgdir/usr/share/licenses/$pkgname/" LICENSE
}
