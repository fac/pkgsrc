# $NetBSD: Makefile,v 1.19 2018/08/22 09:44:29 wiz Exp $

DISTNAME=	PadWalker-2.3
PKGNAME=	p5-${DISTNAME:S/96/9.6/}
PKGREVISION=	1
CATEGORIES=	devel perl5
MASTER_SITES=	${MASTER_SITE_PERL_CPAN:=../../authors/id/R/RO/ROBIN/}

MAINTAINER=	pkgsrc-users@NetBSD.org
HOMEPAGE=	http://search.cpan.org/dist/PadWalker/
COMMENT=	Play with other peoples' lexical variables
LICENSE=	${PERL5_LICENSE}

USE_LANGUAGES=	c
PERL5_PACKLIST= auto/PadWalker/.packlist

.include "../../lang/perl5/module.mk"
.include "../../mk/bsd.pkg.mk"
