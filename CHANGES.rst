Changelog of z3c.dependencychecker
==================================

1.11 (unreleased)
-----------------

- Nothing changed yet.


1.10 (2013-02-24)
-----------------

- Treat non-test extras_require like normal install_requires.


1.9 (2013-02-13)
----------------

- Improved detection for "Django-style" package names with a dash in
  them. Django doesn't deal well with namespace packages, so instead of
  ``zc.something``, you'll see packages like ``zc-something``. The import then
  uses an underscore, ``zc_something``.

- Added support for Django settings files. Anything that matches
  ``*settings.py`` is searched for Django settings like ``INSTALLED_APPS =
  [...]`` or ``MIDDLEWARE_CLASSES = (...)``.


1.8 (2013-02-13)
----------------

- Detect ZCML "provides", as used for generic setup profile registration.


1.7.1 (2012-11-26)
------------------

- Added travis.ci configuration. We're tested there, too, now!


1.7 (2012-11-26)
----------------

- Lookup package name for ZCML modules too, as it is done for python modules.

- Detect generic setup dependencies in ``metadata.xml`` files.


1.6 (2012-11-01)
----------------

- Fix AttributeError when "magic modules" like email.Header are imported.


1.5 (2012-07-03)
----------------

- Add support for zipped dists when looking up pkg name.


1.4 (2012-07-03)
----------------

- Lookup pkg name from egg-infos if possible (python >= 2.5). This helps for
  instance with the PIL problem (which can be ``Imaging`` instead when you
  import it).


1.3.2 (2012-06-29)
------------------

- Fixed broken 1.3.0 and 1.3.0 release: the ``MANIFEST.in`` was missing...


1.3.1 (2012-06-29)
------------------

- Documentation updates because we moved to github:
  https://github.com/reinout/z3c.dependencychecker .


1.3 (2012-06-29)
----------------

- Added fix for standard library detection on OSX when using the python
  buildout. (Patch by Jonas Baumann, as is the next item).

- Supporting ``[tests]`` in addition to ``[test]`` for test requirements.


1.2 (2011-09-19)
----------------

- Looking for a package directory named after the package name in preference
  to the src/ directory.

- Compensating for django-style 'django-something' package names with
  'django_something' package directories.  Dash versus underscore.


1.1 (2010-01-06)
----------------

- Zcml files are also searched for 'component=' patterns as that can be used
  by securitypolicy declarations.

- Dependencychecker is now case insensitive as pypi is too.

- Using optparse for parsing commandline now.  Added --help and --version.


1.0 (2009-12-10)
----------------

- Documentation update.

- Improved test coverage. The dependencychecker module self is at 100%, the
  original import checker module is at 91% coverage.


0.5 (2009-12-10)
----------------

- Searching in doctests (.py, .txt, .rst) for imports, too.  Regex-based by
  necessity, but it seems to catch what I can test it with.


0.4 (2009-12-10)
----------------

- Supporting "from zope import interface"-style imports where you really want
  to be told you're missing an "zope.interface" dependency instead of just
  "zope" (which is just a namespace package).


0.3 (2009-12-08)
----------------

- Sorted "unneeded requirements" reports and filtered out duplicates.

- Reporting separately on dependencies that should be moved from the regular
  to the test dependencies.


0.2 (2009-12-08)
----------------

- Added tests.  Initial quick test puts coverage at 86%.

- Fixed bug in test requirement detection.

- Added documentation.

- Moved source code to zope's svn repository.


0.1 (2009-12-02)
----------------

- Also reporting on unneeded imports.

- Added note on re-running buildout after a setup.py change.

- Added zcml lookup to detect even more missing imports.

- Added reporting on missing regular and test imports.

- Grabbing existing requirements from egginfo directory.

- Copied over Martijn Faassen's zope importchecker script.
