# Created by: Erik B Knudsen <erkn@fysik.dtu.dk>
# $FreeBSD: head/science/mcstas/Makefile 401313 2015-11-12 02:29:59Z junovitch $

PORTNAME=	mcstas
PORTVERSION=	2.2a
CATEGORIES=	science
MASTER_SITES=	http://download.mcstas.org/${PORTNAME}-${PORTVERSION}/unix/McStas-${PORTVERSION}-UNIX-src/
DISTNAME=	mcstas-${PORTVERSION}-src

MAINTAINER=	erkn@fysik.dtu.dk
COMMENT=	Monte Carlo neutron ray tracing package

LICENSE=	GPLv2

USES=		bison:build cmake gmake
CMAKE_ARGS=	"-Denable_mcstas=1"
GNU_CONFIGURE=	yes

PLIST_SUB+=	PORTVERSION=${PORTVERSION}
SUB_FILES=	pkg-deinstall pkg-install

post-stage:
	${STRIP_CMD} ${STAGEDIR}${PREFIX}/mcstas/${PORTVERSION}/bin/mcformat
	${STRIP_CMD} ${STAGEDIR}${PREFIX}/mcstas/${PORTVERSION}/bin/mcstas

.include <bsd.port.mk>
