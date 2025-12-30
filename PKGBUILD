# SPDX-License-Identifier: AGPL-3.0

#    ----------------------------------------------------------------------
#    Copyright © 2024, 2025  Pellegrino Prevete
#
#    All rights reserved
#    ----------------------------------------------------------------------
#
#    This program is free software: you can redistribute it and/or modify
#    it under the terms of the GNU Affero General Public License as published by
#    the Free Software Foundation, either version 3 of the License, or
#    (at your option) any later version.
#
#    This program is distributed in the hope that it will be useful,
#    but WITHOUT ANY WARRANTY; without even the implied warranty of
#    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
#    GNU Affero General Public License for more details.
#
#    You should have received a copy of the GNU Affero General Public License
#    along with this program.  If not, see <https://www.gnu.org/licenses/>.

# Maintainers:
#   Truocolo
#     <truocolo@aol.com>
#     <truocolo@0x6E5163fC4BFc1511Dbe06bB605cc14a3e462332b>
#   Pellegrino Prevete (dvorak)
#     <pellegrinoprevete@gmail.com>
#     <dvorak@0x87003Bd6C074C713783df04f36517451fF34CBEf>

_evmfs_available="$( \
  command \
    -v \
    "evmfs" || \
    true)"
if [[ ! -v "_evmfs" ]]; then
  if [[ "${_evmfs_available}" != "" ]]; then
    _evmfs="true"
  elif [[ "${_evmfs_available}" == "" ]]; then
    _evmfs="false"
  fi
fi
_os="$( \
  uname \
    -o)"
if [[ ! -v "_git" ]]; then
  _git="false"
fi
if [[ ! -v "_offline" ]]; then
  _offline="false"
fi
if [[ ! -v "_git_http" ]]; then
  _git_http="gitlab"
fi
if [[ "${_git_http}" == "github" ]]; then
  _archive_format="zip"
elif [[ "${_git_http}" == "gitlab" ]]; then
  _archive_format="tar.gz"
fi
if [[ ! -v "_docs" ]]; then
  _docs="true"
fi
_pkg=ucantellme
pkgbase="${_pkg}"
pkgname=(
  "${_pkg}"
)
if [[ "${_docs}]" == "true" ]]; then
  pkgname+=(
    "${_pkg}-docs"
  )
fi
pkgver=0.0.0.0.0.0.0.0.0.0.0.0.0.1.1
_commit="cf98fb7d48cc3145c5c9b827f6eebbd6679b1674"
pkgrel=5
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
if [[ "${_os}" != "GNU/Linux" ]] && \
   [[ "${_os}" == "Android" ]]; then
  depends+=(
  )
fi
_zenity_optdepends=(
  "zenity:"
    "simple graphical prompt support"
)
_systemd_ask_password_optdepends=(
  "systemd-ask-password:"
    "theres no real reason huge chunks of systemd"
    "should not be cross-platform."
)
optdepends=(
  "${_zenity_optdepends[*]}"
  "${_systemd_ask_password_optdepends[*]}"
)
if [[ "${_os}" == "GNU/Linux" ]] && \
   [[ "${_os}" != "Android" ]]; then
  optdepends+=(
  )
fi
makedepends=(
  "make"
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
_sum="fb0c1c8cd66760e4c3fd50bf19f3f0b6da8911e3bc8042c8adadf9332639feff"
_sig_sum="4fc41eeb4481b3df9388d637a3c7983609ebfadd7d262066e8cf9536c227ac5c"
_github_sum='6a25e561ab17fb2d854e198433bac03532018560428e78c0f802604960561926'
_evmfs_ns="0x87003Bd6C074C713783df04f36517451fF34CBEf"
_evmfs_network="100"
_evmfs_address="0x69470b18f8b8b5f92b48f6199dcb147b4be96571"
_evmfs_uri="evmfs://${_evmfs_network}/${_evmfs_address}/${_evmfs_ns}/${_sum}"
_evmfs_src="${_tarname}.${_archive_format}::${_evmfs_uri}"
_sig_uri="evmfs://${_evmfs_network}/${_evmfs_address}/${_evmfs_ns}/${_sig_sum}"
_sig_src="${_tarname}.${_archive_format}.sig::${_sig_uri}"
source=()
sha256sums=()
if [[ "${_evmfs}" == "true" ]]; then
  if [[ "${_git}" == "false" ]]; then
    _src="${_evmfs_src}"
    source+=(
      "${_sig_src}"
    )
    sha256sums+=(
      "${_sig_sum}"
    )
  fi
elif [[ "${_evmfs}" == "false" ]]; then
  if [[ "${_git}" == true ]]; then
    _src="${_tarname}::git+${_url}#${_tag_name}=${_tag}?signed"
    _sum="SKIP"
  elif [[ "${_git}" == false ]]; then
    _uri=""
    if [[ "${_git_service}" == "github" ]]; then
      if [[ "${_tag_name}" == "commit" ]]; then
        _uri="${_url}/archive/${_commit}.${_archive_format}"
        _sum="${_github_sum}"
      fi
    elif [[ "${_git_service}" == "gitlab" ]]; then
      if [[ "${_tag_name}" == "commit" ]]; then
        _uri="${_url}/-/archive/${_tag}/${_tag}.${_archive_format}"
      fi
    fi
    _src="${_tarfile}::${_uri}"
  fi
fi
source+=(
  "${_src}"
)
sha256sums+=(
  "${_sum}"
)
validpgpkeys=(
  # Truocolo
  #   <truocolo@aol.com>
  '97E989E6CF1D2C7F7A41FF9F95684DBE23D6A3E9'
  #   <truocolo@0x6E5163fC4BFc1511Dbe06bB605cc14a3e462332b>
  'F690CBC17BD1F53557290AF51FC17D540D0ADEED'
  # Pellegrino Prevete (dvorak)
  #   <dvorak@0x87003Bd6C074C713783df04f36517451fF34CBEf>
  '12D8E3D7888F741E89F86EE0FEC8567A644F1D16'
)

check() {
  local \
    _make_opts=()
  _make_opts+=(
    -k
  )
  cd \
    "${_tarname}"
  make \
    "${_make_opts[@]}" \
    check
}

package_ucantellme() {
  local \
    _make_opts=()
  _make_opts+=(
    PREFIX="/usr"
    DESTDIR="${pkgdir}"
  )
  ls
  cd \
    "${_tarname}"
  make \
    "${_make_opts[@]}" \
    install-scripts
  install \
    -Dm644 \
    "COPYING" \
    -t \
    "${pkgdir}/usr/share/licenses/${pkgname}/"
}

package_evm-contracts-tools-docs() {
  local \
    _make_opts=()
  _make_opts+=(
    PREFIX="/usr"
    DESTDIR="${pkgdir}"
  )
  cd \
    "${_tarname}"
  make \
    "${_make_opts[@]}" \
    install-doc
  make \
    "${_make_opts[@]}" \
    install-man
  install \
    -Dm644 \
    "COPYING" \
    -t \
    "${pkgdir}/usr/share/licenses/${pkgname}/"
}

# vim: ft=sh syn=sh et
