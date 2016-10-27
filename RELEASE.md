Pypi
====

Preparation:

* run unit tests: `tests/wekatests/all_tests.py`
* increment version in `setup.py`
* increment versions in `doc/source/conf.py`
* update API documentation

  * cd python/weka
  * sphinx-apidoc -f -o ../../doc/source .
  * make sure that all modules are included in `index.rst` (apart from `modules.rst`)

* add new changelog section in `CHANGES.rst`
* commit/push all changes

When upgrading Weka version:

* change download URL in method `download_weka()` in `setup.py`

Commands for releasing on pypi.org:

```
  find -name "*~" -delete
  python3 setup.py clean
  python3 setup.py sdist upload
  cd doc
  make html
  create zip of doc/buid/html, replace html/pypi/sphinx.zip and upload on pypi.org
```


Github
======

Steps:

* start new release (version: `vX.Y.Z`)
* enter release notes, i.e., significant changes since last release
* upload `python-weka-wrapper3-X.Y.Z.tar.gz` previously generated with `setyp.py`
* publish


ReadTheDocs
===========

Make documentation for new version public on
[readthedocs.org](https://readthedocs.org/projects/python-weka-wrapper3/).


MLOSS
=====

Steps:

* login
* goto project page https://mloss.org/software/view/660/
* click on `Update project`
* update `Version` and `Download URL`
* re-use release notes from Github release in `Changes since last revision`
* save


Google Group
============

* post release on the Google Group: https://groups.google.com/forum/#!forum/python-weka-wrapper
