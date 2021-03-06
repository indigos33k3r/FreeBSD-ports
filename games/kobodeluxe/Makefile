# Created by: Amar Takhar <verm@drunkmonk.net>
# $FreeBSD$

PORTNAME=	kobodeluxe
PORTVERSION=	0.5.1
PORTREVISION=	13
CATEGORIES=	games
MASTER_SITES=	http://olofson.net/kobodl/download/ \
		http://mirror.amdmi3.ru/distfiles/
DISTNAME=	KoboDeluxe-${DISTVERSION}

MAINTAINER=	amdmi3@FreeBSD.org
COMMENT=	SDL port of the scrolling game XKobo

USES=		compiler tar:bzip2
USE_SDL=	image sdl
GNU_CONFIGURE=	yes
CONFIGURE_ARGS=	--sharedstatedir=${SCOREDIR} --enable-oss

CXXFLAGS+=	${CXXFLAGS_${CHOSEN_COMPILER_TYPE}}
CXXFLAGS_clang=	-Wno-reserved-user-defined-literal

SCOREDIR=	/var/games/${PORTNAME}

SUB_FILES=	pkg-deinstall pkg-install
SUB_LIST=	SCOREDIR="${SCOREDIR}"

DATADIR=	${PREFIX}/share/kobo-deluxe
PORTDOCS=	*
PORTDATA=	*

OPTIONS_DEFINE=	DOCS OPENGL
OPTIONS_DEFAULT=OPENGL

OPENGL_USE=	GL=gl
OPENGL_CONFIGURE_ENABLE=	opengl

post-extract:
	@cd ${WRKSRC} && ${TAR} -xzf icons.tar.gz

post-patch:
	@${REINPLACE_CMD} -e 's|$$(datadir)/games/kobo-deluxe|${DATADIR}|; \
		s|$$(prefix)/games/kobo-deluxe/scores|${SCOREDIR}|; \
		s|-lSDL$$||; s|SDL/SDL|SDL|' ${WRKSRC}/configure
	@${REINPLACE_CMD} -e 's|$$(datadir)/games/kobo-deluxe|${DATADIR}|' \
		${WRKSRC}/data/Makefile.in
	@${REINPLACE_CMD} -e 's|pipe2|kobopipe2|g' ${WRKSRC}/enemies.h \
		${WRKSRC}/enemy.cpp

post-install:
	@${RM} -r ${STAGEDIR}/var
	${INSTALL_DATA} ${WRKSRC}/icons/Ubuntu/kobodeluxe.desktop \
		${STAGEDIR}${PREFIX}/share/applications/
	${INSTALL_DATA} ${WRKSRC}/icons/Ubuntu/kobo-icon.xpm \
		${STAGEDIR}${PREFIX}/share/pixmaps/

post-install-DOCS-on:
	@${MKDIR} ${STAGEDIR}${DOCSDIR}
	${INSTALL_DATA} ${WRKSRC}/README ${STAGEDIR}${DOCSDIR}

.include <bsd.port.mk>
