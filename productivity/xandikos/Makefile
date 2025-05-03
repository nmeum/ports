COMMENT =	Git-backed CalDAV calendar server

MODPY_DISTV =	0.2.12
DISTNAME =	xandikos-${MODPY_DISTV}
CATEGORIES =	productivity net

HOMEPAGE =	https://github.com/jelmer/xandikos

# GPLv3+
PERMIT_PACKAGE =	Yes

MODULES =	lang/python
MODPY_PI =	Yes
MODPY_PYBUILD =	setuptools

RUN_DEPENDS =	devel/py-dulwich \
		www/py-aiohttp \
		textproc/py-defusedxml \
		devel/py-icalendar \
		www/py-jinja2 \
		textproc/py-vobject

# Two tests in test_icalendar.py require a newer py3-icalendar version.
MODPY_PYTEST_ARGS =	--ignore xandikos/tests/test_icalendar.py

post-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/xandikos
	cd ${WRKSRC}; ${INSTALL_DATA} COPYING README.rst GOALS.rst \
	    ${PREFIX}/share/doc/xandikos

.include <bsd.port.mk>
