# $NetBSD: Makefile,v 1.19 2018/04/13 16:59:13 he Exp $

DISTNAME=	rssh-2.3.4
PKGREVISION= 2
CATEGORIES=	shells security
MASTER_SITES=	${MASTER_SITE_SOURCEFORGE:=rssh/}

MAINTAINER=	pkgsrc-users@NetBSD.org
HOMEPAGE=	http://www.pizzashack.org/rssh/
COMMENT=	Restricted shell allowing only scp and/or sftp
LICENSE=	2-clause-bsd

GNU_CONFIGURE=		yes
CONFIGURE_ARGS+=	--sysconfdir=${PKG_SYSCONFDIR}

.if !exists(/usr/include/wordexp.h)
PKG_FAIL_REASON+=	"${PKGNAME} requires wordexp(3)"
.endif

EGDIR=			${PREFIX}/share/examples/rssh
INSTALLATION_DIRS=	share/examples/rssh
CONF_FILES=		${EGDIR}/rssh.conf ${PKG_SYSCONFDIR}/rssh.conf
PKG_SHELL?=		bin/rssh

SPECIAL_PERMS+=	${PREFIX}/libexec/rssh_chroot_helper ${SETUID_ROOT_PERMS}

BUILD_DEFS+=		RSSH_SCP_PATH
BUILD_DEFS+=		RSSH_SFTP_SERVER_PATH
BUILD_DEFS+=		RSSH_CVS_PATH
BUILD_DEFS+=		RSSH_RDIST_PATH
BUILD_DEFS+=		RSSH_RSYNC_PATH

.if defined(RSSH_SCP_PATH) && !empty(RSSH_SCP_PATH)
CONFIGURE_ARGS+=	--with-scp=${RSSH_SCP_PATH:Q}
.endif
.if defined(RSSH_SFTP_SERVER_PATH) && !empty(RSSH_SFTP_SERVER_PATH)
CONFIGURE_ARGS+=	--with-sftp-server=${RSSH_SFTP_SERVER_PATH:Q}
.endif
.if defined(RSSH_CVS_PATH) && !empty(RSSH_CVS_PATH)
CONFIGURE_ARGS+=	--with-cvs=${RSSH_CVS_PATH:Q}
.endif
.if defined(RSSH_RDIST_PATH) && !empty(RSSH_RDIST_PATH)
CONFIGURE_ARGS+=	--with-rdist=${RSSH_RDIST_PATH:Q}
.endif
.if defined(RSSH_RSYNC_PATH) && !empty(RSSH_RSYNC_PATH)
CONFIGURE_ARGS+=	--with-rsync=${RSSH_RSYNC_PATH:Q}
.endif

CONFIGURE_ARGS.SunOS+=	--disable-static

post-install:
	${INSTALL_DATA} ${WRKSRC}/rssh.conf.default ${DESTDIR}${EGDIR}/rssh.conf

.include "../../mk/bsd.pkg.mk"
