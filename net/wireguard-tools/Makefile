COMMENT=		tools for use with WireGuard VPN

DISTNAME=		wireguard-tools-1.0.20210914
EPOCH=			0
REVISION=		4

CATEGORIES=		net security

HOMEPAGE=		https://www.wireguard.com/

MAINTAINER=		Jose G Perez Taveras <josegpt27@gmail.com>

# GPLv2 only
PERMIT_PACKAGE=		Yes

WANTLIB+= c

SITES=			https://git.zx2c4.com/wireguard-tools/snapshot/

EXTRACT_SUFX=		.tar.xz


# Uses __builtin_bswap* on big-endian archs
COMPILER=		base-clang ports-gcc
COMPILER_LANGS=		c

MAKE_FLAGS=		WITH_WGQUICK=yes \
			WITH_BASHCOMPLETION=no \
			V=1
FAKE_FLAGS=		MANDIR=${PREFIX}/man \
			PREFIX=${PREFIX}
USE_GMAKE=		Yes

NO_TEST=		Yes

WRKSRC=			${WRKDIST}/src

ALL_TARGET=		wg

post-extract:
	sed -i 's/install -v /install /g' ${WRKSRC}/Makefile

.include <bsd.port.mk>
