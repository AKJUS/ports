COMMENT=	functions for working with Ansible from Python

MODPY_DISTV=	25.6.0
DISTNAME=	ansible_compat-${MODPY_DISTV}
PKGNAME=	py-ansible-compat-${MODPY_DISTV}

CATEGORIES=	sysutils

# BSD
PERMIT_PACKAGE=	Yes

MODULES=	lang/python
MODPY_PYBUILD=	setuptools_scm
MODPY_PI=	Yes

RUN_DEPENDS=	sysutils/py-packaging \
		textproc/py-yaml \
		sysutils/py-subprocess-tee \
		devel/py-jsonschema

# some tests require network
PORTHOME=	${WRKDIR}
TEST_DEPENDS=	${FULLPKGNAME}:${BUILD_PKGPATH} \
		devel/py-flaky \
		devel/py-test-mock

.include <bsd.port.mk>
