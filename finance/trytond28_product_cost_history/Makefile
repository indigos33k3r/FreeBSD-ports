# Created by: Matthias Petermann <matthias@petermann-it.de>
# $FreeBSD$

PORTNAME=	trytond28_product_cost_history
PORTVERSION=	2.8.0
PORTREVISION=	2
CATEGORIES=	finance python
MASTER_SITES=	https://pypi.python.org/packages/source/t/trytond_product_cost_history/ \
		http://downloads.tryton.org/${PORTVERSION:R}/
DISTNAME=	trytond_product_cost_history-${PORTVERSION}

MAINTAINER=	matthias@petermann-it.de
COMMENT=	Tryton Application Platform (Product Cost History Module)

LICENSE=	GPLv3

RUN_DEPENDS=	trytond28_product>=2.8.0:finance/trytond28_product

CONFLICTS=	trytond_product_cost_history-2.[46].*

USES=		python:2.7
USE_PYTHON=	distutils autoplist

.include <bsd.port.mk>
