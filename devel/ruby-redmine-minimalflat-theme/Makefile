# $NetBSD: Makefile,v 1.4 2017/09/16 19:26:49 wiz Exp $
#

GITHUB_TAG=	v1.0.2
DISTNAME=	${GITHUB_TAG}
GITHUB_PROJECT=	redmine-theme-minimalflat
PKGNAME=	${RUBY_PKGPREFIX}-redmine-minimalflat-theme-${DISTNAME:S/v//1}
MASTER_SITES=	${MASTER_SITE_GITHUB:=akabekobeko/}
DIST_SUBDIR=	ruby-redmine-minimalflat-theme

MAINTAINER=	pkgsrc-users@NetBSD.org
HOMEPAGE=	https://github.com/akabekobeko/redmine-theme-minimalflat
COMMENT=	Minimal and flat design Redmine theme.
LICENSE=	gnu-gpl-v2

.include "../../meta-pkgs/ruby-redmine-themes/Makefile.common"

MINIMALFLAT_DIR=	${REDMINE_THEMEDIR}/minimalflat

INSTALLATION_DIRS+=	${MINIMALFLAT_DIR}/fonts ${MINIMALFLAT_DIR}/javascripts
INSTALLATION_DIRS+=	${MINIMALFLAT_DIR}/stylesheets

do-install:
	for i in fonts javascripts stylesheets; do \
		${INSTALL_DATA} ${WRKSRC}/$$i/* \
			${DESTDIR}${PREFIX}/${MINIMALFLAT_DIR}/$$i; \
	done

.include "../../lang/ruby/rubyversion.mk"
.include "../../mk/bsd.pkg.mk"
