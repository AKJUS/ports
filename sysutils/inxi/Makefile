PKG_ARCH =	*

COMMENT =	full featured CLI system information tool

DIST_TUPLE =	codeberg smxi inxi 3.3.41-1 .
WRKDIST =	${WRKDIR}/inxi
PKGNAME =	inxi-3.3.41pl1

CATEGORIES =	sysutils

MAINTAINER =	izzy Meyer <izder456@disroot.org>

# GPLv3+
PERMIT_PACKAGE =	Yes

NO_BUILD =		Yes
NO_TEST =		Yes

do-install:
	${INSTALL_PROGRAM} ${WRKDIST}/inxi ${PREFIX}/bin/
	${INSTALL_MAN} ${WRKDIST}/inxi.1 ${PREFIX}/man/man1/

.include <bsd.port.mk>
