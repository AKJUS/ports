COMMENT =	cross-platform, GPU-accelerated terminal emulator
CATEGORIES =	x11

MAINTAINER =	Eric Auge <eau+obsd@unix4fun.net>

GH_ACCOUNT =	alacritty
GH_PROJECT =	alacritty
GH_TAGNAME =	v0.15.1
REVISION =	1

HOMEPAGE =	https://alacritty.org/

# Apache 2.0
PERMIT_PACKAGE =	Yes

WANTLIB += ${MODCARGO_WANTLIB} fontconfig freetype m util
# xcb and xkbcommon are dlopen()'d
WANTLIB += xcb xkbcommon

MODULES =	devel/cargo \
		lang/python

RUN_DEPENDS =	devel/desktop-file-utils

BUILD_DEPENDS =	textproc/scdoc

LIB_DEPENDS =	x11/xkbcommon

# for riscv64 and powerpc64, please keep: cc >= 1.0.73 and libc >= 0.2.113
MODCARGO_CRATES_UPDATE =	cc libc
MODCARGO_RUSTFLAGS += -L${PREFIX}/lib

MAKE_ENV =	${MODCARGO_ENV}

CONFIGURE_STYLE =	cargo

SEPARATE_BUILD =	Yes

RELEASE_DIR =	${MODCARGO_TARGET_DIR}/release
EXTRA_DIR = 	${WRKSRC}/extra

pre-install:
	scdoc < ${EXTRA_DIR}/man/alacritty.1.scd > ${EXTRA_DIR}/alacritty.1
	scdoc < ${EXTRA_DIR}/man/alacritty.5.scd > ${EXTRA_DIR}/alacritty.5
	scdoc < ${EXTRA_DIR}/man/alacritty-msg.1.scd > ${EXTRA_DIR}/alacritty-msg.1
	scdoc < ${EXTRA_DIR}/man/alacritty-bindings.5.scd > ${EXTRA_DIR}/alacritty-bindings.5

do-install:
	${INSTALL_PROGRAM} ${RELEASE_DIR}/alacritty ${PREFIX}/bin/
	${INSTALL_MAN} ${EXTRA_DIR}/*.1 ${PREFIX}/man/man1/
	${INSTALL_MAN} ${EXTRA_DIR}/*.5 ${PREFIX}/man/man5/
	${INSTALL_DATA_DIR} ${PREFIX}/share/bash-completion/completions
	${INSTALL_DATA} ${EXTRA_DIR}/completions/alacritty.bash \
		${PREFIX}/share/bash-completion/completions/alacritty
	${INSTALL_DATA_DIR} ${PREFIX}/share/fish/vendor_completions.d
	${INSTALL_DATA} ${EXTRA_DIR}/completions/alacritty.fish \
		${PREFIX}/share/fish/vendor_completions.d/
	${INSTALL_DATA_DIR} ${PREFIX}/share/zsh/site-functions
	${INSTALL_DATA} ${EXTRA_DIR}/completions/_alacritty \
		${PREFIX}/share/zsh/site-functions/_alacritty
	${INSTALL_DATA_DIR} ${PREFIX}/share/applications
	${INSTALL_DATA} ${EXTRA_DIR}/linux/Alacritty.desktop \
		${PREFIX}/share/applications/
	${INSTALL_DATA_DIR} ${PREFIX}/share/pixmaps
	${INSTALL_DATA} ${EXTRA_DIR}/logo/alacritty-term.svg \
		${PREFIX}/share/pixmaps/Alacritty.svg
	tic -s -x -o ${PREFIX}/share/terminfo ${EXTRA_DIR}/alacritty.info

.include "crates.inc"

.include <bsd.port.mk>
