# $NetBSD: Makefile,v 1.12 2018/07/03 05:03:10 adam Exp $

DISTNAME=	pydoctor-0.5
PKGNAME=	${DISTNAME:S/py/${PYPKGPREFIX}-/}
CATEGORIES=	devel
MASTER_SITES=	${MASTER_SITE_PYPI:=p/pydoctor/}

MAINTAINER=	pkgsrc-users@NetBSD.org
HOMEPAGE=	https://pypi.python.org/pypi/pydoctor/
COMMENT=	API doc generator
LICENSE=	mit

DEPENDS+=	${PYPKGPREFIX}-nevow>=0.9.18:../../www/py-nevow

USE_LANGUAGES=	# none

PYTHON_VERSIONS_INCOMPATIBLE=	34 35 36 37 # py-xml via py-nevow

.include "../../lang/python/distutils.mk"
.include "../../mk/bsd.pkg.mk"
