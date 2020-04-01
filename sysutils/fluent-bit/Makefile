# Created by: Palle Girgensohn <girgen@FreeBSD.org>
# $FreeBSD: head/sysutils/fluent-bit/Makefile 527238 2020-02-27 08:43:16Z girgen $

PORTNAME=	fluent-bit
DISTVERSIONPREFIX=	v
DISTVERSION=	1.4.2
CATEGORIES=	sysutils

MAINTAINER=	girgen@FreeBSD.org
COMMENT=	Fast and lightweight data forwarder

LICENSE=	APACHE20

USE_GITHUB=     yes
GH_ACCOUNT=	Funzinator

BROKEN_mips=		fails to build: conflicting types for 'restrict'
BROKEN_mips64=		fails to build: conflicting types for 'restrict'
BROKEN_powerpc64=	fails to build: cast from pointer to integer of different size

USES=		cmake:noninja gmake bison pgsql
#WANT_PGSQL=	server:configure
CMAKE_ARGS=	-DFLB_OUT_PGSQL=On 

USE_RC_SUBR=	${PORTNAME}

post-install:
	${MV} ${STAGEDIR}${ETCDIR}/${PORTNAME}.conf ${STAGEDIR}${ETCDIR}/${PORTNAME}.conf.sample
	${MV} ${STAGEDIR}${ETCDIR}/parsers.conf ${STAGEDIR}${ETCDIR}/parsers.conf.sample

.include <bsd.port.mk>
