# XXX PORTROACH overriden at end of this file.

COMMENT=	framework to access various sources of multimedia content

GNOME_PROJECT=	grilo
GNOME_VERSION=	0.3.19
API=		0.3

SUBST_VARS=	API

SHARED_LIBS += grilo-0.3                 0.2 # 0.319.1
SHARED_LIBS += grlnet-0.3                0.0 # 0.319.0
SHARED_LIBS += grlpls-0.3                0.0 # 0.319.0

CATEGORIES+=	multimedia

# LGPLv2.1
PERMIT_PACKAGE=	Yes

WANTLIB += c gdk-3 gio-2.0 glib-2.0 gmodule-2.0 gobject-2.0 gtk-3
WANTLIB += intl oauth soup-3.0 totem-plparser

MODULES=	devel/meson \
		x11/gnome

DEBUG_PACKAGES =${BUILD_PACKAGES}

LIB_DEPENDS=	devel/libsoup3 \
		net/liboauth \
		x11/gnome/totem-pl-parser \
		x11/gtk+3

MODGNOME_TOOLS=	gobject-introspection vala

CONFIGURE_ARGS=	-Denable-gtk-doc=false

# Own the grilo plugins directory to prevent warnings that this
# directory does not exist when no plugin is installed.
post-install:
	${INSTALL_DATA_DIR} ${PREFIX}/lib/grilo-${API}

.include <bsd.port.mk>

# Override PORTROACH from gnome.port.mk since we track 0.3.x
PORTROACH=	#empty
