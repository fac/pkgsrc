# $NetBSD: Makefile,v 1.10 2018/10/19 20:28:25 leot Exp $
#
# Note to packagers:
# packages installing additional completion files should drop
# them into ${DESTDIR}${PREFIX}/share/bash-completion.d
# with the name of the package as file name.

DISTNAME=	bash-completion-2.8
CATEGORIES=	shells
MASTER_SITES=	${MASTER_SITE_GITHUB:=scop/}
GITHUB_RELEASE= ${PKGVERSION_NOREV}
EXTRACT_SUFX=	.tar.xz

MAINTAINER=	pkgsrc-users@NetBSD.org
HOMEPAGE=	http://bash-completion.alioth.debian.org/
COMMENT=	Programmable completion specifications for bash
LICENSE=	gnu-gpl-v2

USE_TOOLS+=	bash:run gmake

USE_LANGUAGES=	# none
GNU_CONFIGURE=	yes

SUBST_CLASSES+=		path
SUBST_SED.path+=	-e "s,/etc/bash_completion.d,${PREFIX}/share/bash-completion.d,g"
SUBST_SED.path+=	-e "s,/etc/bash_completion,${PREFIX}/share/bash-completion/bash_completion,g"
SUBST_STAGE.path=	pre-build
SUBST_FILES.path+=	README
SUBST_MESSAGE.path=	Fixing path to completion files.

.include "../../mk/bsd.pkg.mk"
