# $NetBSD: Makefile,v 1.11 2018/04/17 01:57:18 christos Exp $

PKGNAME=	${DISTNAME:S/cyrus-sasl/cy2-plain/}
#PKGREVISION=	1
COMMENT=	Cyrus SASL PLAIN authentication plugin
SASL_PLUGIN=	yes

CONFLICTS=	cyrus-sasl<=2.1.19nb1

.include "../../security/cyrus-sasl/Makefile.common"

CONFIGURE_ARGS+=	--enable-plain

BUILD_DIRS=	plugins
BUILD_TARGET=	libplain.la

do-install:
	${INSTALL_DATA_DIR} ${DESTDIR}${PLUGINDIR}
	cd ${WRKSRC}/plugins && ${SHLIBTOOL} --mode=install		\
		${INSTALL_PROGRAM} libplain.la ${DESTDIR}${PLUGINDIR}

.include "../../mk/bsd.pkg.mk"
