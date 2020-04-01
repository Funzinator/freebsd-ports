# $FreeBSD$

PORTNAME=	fluent-bit
DISTVERSIONPREFIX=	v
DISTVERSION=	1.4.1-1
CATEGORIES=	sysutils

MAINTAINER=	girgen@FreeBSD.org
COMMENT=	Fast and lightweight data forwarder

LICENSE=	APACHE20

USES=		cmake:noninja gmake bison

USE_GITHUB=     yes
GH_ACCOUNT=	Funzinator

OPTIONS_DEFINE=		KAFKA PGSQL SSL
OPTIONS_DEFAULT=	PGSQL SSL

BROKEN_mips=		fails to build: conflicting types for 'restrict'
BROKEN_mips64=		fails to build: conflicting types for 'restrict'
BROKEN_powerpc64=	fails to build: cast from pointer to integer of different size

CMAKE_ARGS=	-DFLB_DEBUG=Off -DFLB_TRACE=Off -DFLB_CORO_STACK_SIZE=24576

SSL_USES=		ssl
SSL_CMAKE_ON=		-DFLB_TLS=On
SSL_CMAKE_OFF=		-DFLB_TLS=Off

EXAMPLES_CMAKE_ON=	-DFLB_EXAMPLES=On
EXAMPLES_CMAKE_OFF=	-DFLB_EXAMPLES=Off

PGSQL_USES=		pgsql
PGSQL_DESC=		PostgreSQL output plugin
PGSQL_CMAKE_ON=		-DFLB_OUT_PGSQL=On
PGSQL_CMAKE_OFF=	-DFLB_OUT_PGSQL=Off

KAFKA_DESC=		Kafka output plugin
KAFKA_CMAKE_ON=		-DFLB_OUT_KAFKA=On
KAFKA_CMAKE_OFF=	-DFLB_OUT_KAFKA=Off

USE_RC_SUBR=	${PORTNAME}

post-install:
	${MV} ${STAGEDIR}${ETCDIR}/${PORTNAME}.conf ${STAGEDIR}${ETCDIR}/${PORTNAME}.conf.sample
	${MV} ${STAGEDIR}${ETCDIR}/parsers.conf ${STAGEDIR}${ETCDIR}/parsers.conf.sample

.include <bsd.port.mk>
