# SPDX-License-Identifier: AGPL-3.0
#
# Maintainer: Truocolo <truocolo@aol.com>
# Maintainer: Pellegrino Prevete (tallero) <pellegrinoprevete@gmail.com>

_offline="false"
_git="false"
pkgname=ucantellme
pkgver=0.0.0.0.0.0.0.0.0.0.0.0.0.1
_commit="c69c1e46b77c876a48cd20d2d0ccc1af8ad44dfd"
pkgrel=1
_pkgdesc=(
  "Passphrase prompter."
)
pkgdesc="${_pkgdesc[*]}"
arch=(
  any
)
_http="https://github.com"
_ns="themartiancompany"
url="${_http}/${_ns}/${pkgname}"
license=(
  AGPL3
)
depends=(
  "bash"
  "libcrash-bash"
)
_os="$( \
  uname \
    -o)"
[[ "${_os}" != "GNU/Linux" ]] && \
[[ "${_os}" == "Android" ]] && \
  depends+=(
  )
optdepends=(
  'zenity: graphical prompt'
  "systemd-ask-password: theres no real reason huge chunks of systemd should not be cross-platform"
)
[[ "${_os}" == "GNU/Linux" ]] && \
[[ "${_os}" != "Android" ]] && \
  optdepends+=(
  )
makedepends=(
  make
)
checkdepends=(
  "shellcheck"
)
source=()
sha256sums=()
_url="${url}"
_tag="${_commit}"
_tag_name="commit"
_tarname="${pkgname}-${_tag}"
[[ "${_offline}" == "true" ]] && \
  url="file://${HOME}/${pkgname}"
[[ "${_git}" == true ]] && \
  makedepends+=(
    "git"
  ) && \
  source+=(
    "${_tarname}::git+${_url}#${_tag_name}=${_tag}?signed"
  ) && \
  sha256sums+=(
    SKIP
  )
[[ "${_git}" == false ]] && \
  if [[ "${_tag_name}" == 'pkgver' ]]; then
    _tar="${_tarname}.tar.gz::${_url}/archive/refs/tags/${_tag}.tar.gz"
    _sum="fe7dbded528bcfc452021bc2d8f909218ff47cfc2cc31a626446be16f58e5e58"
  elif [[ "${_tag_name}" == "commit" ]]; then
    _tar="${_tarname}.zip::${_url}/archive/${_commit}.zip"
    _sum="fe7dbded528bcfc452021bc2d8f909218ff47cfc2cc31a626446be16f58e5e58"
  fi && \
    source+=(
      "${_tar}"
    ) && \
    sha256sums+=(
      "${_sum}"
    )
validpgpkeys=(
  # Truocolo <truocolo@aol.com>
  '97E989E6CF1D2C7F7A41FF9F95684DBE23D6A3E9'
)

check() {
  cd \
    "${_tarname}"
  make \
    -k \
    check
}

package() {
  cd \
    "${_tarname}"
  make \
    PREFIX="/usr" \
    DESTDIR="${pkgdir}" \
    install
}

# vim: ft=sh syn=sh et
