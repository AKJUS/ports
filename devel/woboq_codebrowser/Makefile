COMMENT =	generator for the woboq code browser

DISTNAME =	woboq_codebrowser-2.1pl20250221

GH_ACCOUNT =	KDAB
GH_PROJECT =	codebrowser
# support LLVM version we have in ports
GH_COMMIT =	9c819d5072dba9ba8eb07646d712b46229f7ecb5

CATEGORIES =	devel

HOMEPAGE =	https://woboq.com/codebrowser.html

# Commercial or CC-BY-NC-SA 3.0
# (you may not use the material for commercial purposes)
#
# https://woboq.com/codebrowser.html
# "If you are interested in hosting a browsable version of your own C/C++
# source code on your website or intranet, you can purchase a license of
# our code browser generator."
#
PERMIT_PACKAGE =	Yes

# uses pledge()
WANTLIB =		${COMPILER_LIBCXX} c m llvm${MODCLANG_VERSION}/lib/clang-cpp

COMPILER =		base-clang ports-clang

MODULES =		devel/cmake \
			lang/clang
LIB_DEPENDS =		${MODCLANG_LIB_DEPENDS}
MODCLANG_RUNDEP =	Yes
MODCLANG_VERSION =	19

NO_TEST =		Yes

CONFIGURE_ARGS +=	-DLLVM_DIR=${LOCALBASE}/llvm${MODCLANG_VERSION}/lib/cmake/llvm

post-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/woboq_codebrowser
	${INSTALL_DATA} ${WRKSRC}/README.md ${PREFIX}/share/doc/woboq_codebrowser

.include <bsd.port.mk>
