# $NetBSD: Makefile,v 1.28 2018/02/11 15:43:18 wiz Exp $

DISTNAME=	i2cb-6.0_ALPHA
PKGREVISION=	7
CATEGORIES=	chat
MASTER_SITES=	${MASTER_SITE_LOCAL}

MAINTAINER=	pkgsrc-users@NetBSD.org
HOMEPAGE=	https://www.draga.com/~jwise/i2cb/
COMMENT=	Next generation Internet Citicen's Band chat client

WRKSRC=		${WRKDIR}/icb

CFLAGS.SunOS+=	-DBSD_COMP
LIBS.SunOS+=	-lsocket

MAKE_ENV+=	LIBS=${LIBS:Q}

INSTALLATION_DIRS=	bin libdata

post-extract:
		${RM} -f ${WRKSRC}/src/.depend

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/src/icb ${DESTDIR}${PREFIX}/bin/i2cb
	${INSTALL_SCRIPT} ${WRKSRC}/icbserverdb \
		${DESTDIR}${PREFIX}/libdata/i2cbserverdb
	${INSTALL_DATA_DIR} ${DESTDIR}${PREFIX}/libdata/i2cb
	${INSTALL_SCRIPT} ${WRKSRC}/sample.icbrc \
		${DESTDIR}${PREFIX}/libdata/i2cb/sample.i2cbrc
	${INSTALL_SCRIPT} \
		${WRKSRC}/contrib/bartender \
		${WRKSRC}/contrib/confuse \
		${WRKSRC}/contrib/echofile \
		${DESTDIR}${PREFIX}/libdata/i2cb

.include "../../lang/tcl/buildlink3.mk"
.include "../../devel/readline/buildlink3.mk"
.include "../../mk/bsd.pkg.mk"
