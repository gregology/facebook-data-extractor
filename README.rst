============
Facebook ETL
============

.. image:: https://badge.fury.io/py/fbetl.svg
    :target: https://badge.fury.io/py/fbetl

.. image:: http://img.shields.io/badge/license-MIT-yellow.svg?style=flat
    :target: https://github.com/gregology/fbetl/blob/master/LICENSE

.. image:: https://img.shields.io/badge/contact-Gregology-blue.svg?style=flat
    :target: http://gregology.net/contact/



Overview
--------

Extracts, transforms, and loads your Facebook data from the [**Download Your Information**](https://www.facebook.com/settings?tab=your_facebook_information) tool into an SQLite DB.

Installation
------------

``fbetl`` is available on PyPI

http://pypi.python.org/pypi/fbetl

Install via ``pip``
::

    $ pip install fbetl

Or via ``easy_install``
::

    $ easy_install fbetl

Or directly from ``fbetl``'s `git repo <https://github.com/gregology/fbetl>`
::

    $ git clone git://github.com/gregology/fbetl.git
    $ cd fbetl
    $ python setup.py install

Basic usage
-----------
::

    >>> from fbetl import Fbetl
    >>> fbetl = Fbetl('facebook-user')
    >>> fbetl.load_all()
    >>> fbetl.sql('SELECT COUNT(*) FROM comments')[0][0]
    5000
    >>> fbetl.sql('SELECT timestamp FROM posts LIMIT 5;')
    [('2018-07-27 14:04:24',), ('2018-07-23 11:34:12',), ('2018-07-17 09:47:19',), ('2018-07-13 23:56:44',), ('2018-07-12 09:54:13',)]


Running Test
------------
::

    $ python tests/tests.py

Python compatibility
--------------------

Developed for Python 3. May work but not tested in Python 2.
