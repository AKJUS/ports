COMMENT =	framework to implement CMS scanners

DISTNAME =	cms_scanner-0.15.0
CATEGORIES =	security

MAINTAINER =	Sebastian Reitenbach <sebastia@openbsd.org>

# MIT
PERMIT_PACKAGE=	Yes

MODULES =	lang/ruby
WANTLIB =	crypto ssl ${MODRUBY_WANTLIB}
NO_TEST =	Yes

BUILD_DEPENDS +=	${RUN_DEPENDS}
RUN_DEPENDS +=		devel/ruby-get_process_mem,${MODRUBY_FLAVOR},>=0.2.5,<1.1 \
			devel/ruby-ruby-progressbar,${MODRUBY_FLAVOR},>=1.10,<1.14 \
			devel/ruby-opt_parse_validator,${MODRUBY_FLAVOR}>=1.10,<1.11 \
			devel/ruby-yajl,${MODRUBY_FLAVOR},>=1.4.1,<1.5 \
			net/ruby-public_suffix,${MODRUBY_FLAVOR},>=4.0.3,<6.1.0 \
			textproc/ruby-nokogiri,${MODRUBY_FLAVOR},>=1.16,<2 \
			www/ruby-ethon,${MODRUBY_FLAVOR},>=0.14,<0.17 \
			www/ruby-typhoeus,${MODRUBY_FLAVOR},>=1.3,<1.5 \
			www/ruby-xmlrpc,${MODRUBY_FLAVOR},>=0.3,<1

CONFIGURE_STYLE =	ruby gem

.include <bsd.port.mk>
