# $FreeBSD$

PORTNAME=	shelly
PORTVERSION=	1.7.2
PORTREVISION=	2
CATEGORIES=	shells haskell

MAINTAINER=	haskell@FreeBSD.org
COMMENT=	Shell-like (systems) programming in Haskell

LICENSE=	BSD3CLAUSE

DEPRECATED=		Haskell libraries are getting pushed out of the ports tree. If you are using this port for development, consider switching to cabal sandboxes (old way), cabal new-build (new way), or use devel/stack. If you believe this port shouldn't be removed, contact haskell@FreeBSD.org
EXPIRATION_DATE=	2019-04-14

USE_CABAL=	async enclosed-exceptions exceptions>=0.6 lifted-async \
		lifted-base monad-control>=0.3.2 mtl>=2 system-fileio \
		system-filepath>=0.4.7 transformers-base unix-compat

.include "${.CURDIR}/../../lang/ghc/bsd.cabal.mk"
.include <bsd.port.mk>
