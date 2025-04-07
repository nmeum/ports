COMMENT =	Git-backed CalDAV calendar server

MODPY_DISTV =	0.2.12
DISTNAME =	xandikos-${MODPY_DISTV}
DISTFILES =	${DISTNAME}{v${MODPY_DISTV}}.tar.gz
PKGNAME =	${DISTNAME:L}
REVISION =	0
CATEGORIES =	productivity net

HOMEPAGE =	https://xandikos.org/

# GPLv3+
PERMIT_PACKAGE =	Yes

SITES =		https://github.com/jelmer/xandikos/archive/

MODULES =	lang/python
SUBST_VARS =	MODPY_SITEPKG
MODPY_PYBUILD =	setuptools

RUN_DEPENDS =	devel/py-dulwich${MODPY_FLAVOR} \
		www/py-aiohttp${MODPY_FLAVOR} \
		textproc/py-defusedxml${MODPY_FLAVOR} \
		devel/py-icalendar${MODPY_FLAVOR} \
		www/py-jinja2${MODPY_FLAVOR} \
		textproc/py-vobject${MODPY_FLAVOR}

MODPY_PYTEST =	Yes
# Two tests in test_icalendar.py require a newer py3-icalendar version.
MODPY_PYTEST_ARGS =	--ignore xandikos/tests/test_icalendar.py

post-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/xandikos
	cd ${WRKSRC}; ${INSTALL_DATA} COPYING NEWS README.rst SUPPORT.md \
	    ${PREFIX}/share/doc/xandikos

.include <bsd.port.mk>
