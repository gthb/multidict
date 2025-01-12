=========
multidict
=========

.. image:: https://dev.azure.com/aio-libs/multidict/_apis/build/status/CI?branchName=master
   :target: https://dev.azure.com/aio-libs/multidict/_build
   :alt: Azure Pipelines status for master branch

.. image:: https://codecov.io/gh/aio-libs/multidict/branch/master/graph/badge.svg
   :target: https://codecov.io/gh/aio-libs/multidict
   :alt: Coverage metrics

.. image:: https://img.shields.io/pypi/v/multidict.svg
   :target: https://pypi.org/project/multidict
   :alt: PyPI

.. image:: https://readthedocs.org/projects/multidict/badge/?version=latest
   :target: http://multidict.readthedocs.org/en/latest/?badge=latest
   :alt: Documentationb

.. image:: https://img.shields.io/pypi/pyversions/multidict.svg
   :target: https://pypi.org/project/multidict
   :alt: Python versions

.. image:: https://badges.gitter.im/Join%20Chat.svg
   :target: https://gitter.im/aio-libs/Lobby
   :alt: Chat on Gitter

Multidict is dict-like collection of *key-value pairs* where key
might be occurred more than once in the container.

Introduction
------------

*HTTP Headers* and *URL query string* require specific data structure:
*multidict*. It behaves mostly like a regular ``dict`` but it may have
several *values* for the same *key* and *preserves insertion ordering*.

The *key* is ``str`` (or ``istr`` for case-insensitive dictionaries).

``multidict`` has four multidict classes:
``MultiDict``, ``MultiDictProxy``, ``CIMultiDict``
and ``CIMultiDictProxy``.

Immutable proxies (``MultiDictProxy`` and
``CIMultiDictProxy``) provide a dynamic view for the
proxied multidict, the view reflects underlying collection changes. They
implement the ``collections.abc.Mapping`` interface.

Regular mutable (``MultiDict`` and ``CIMultiDict``) classes
implement ``collections.abc.MutableMapping`` and allows to change
their own content.


*Case insensitive* (``CIMultiDict`` and
``CIMultiDictProxy``) ones assume the *keys* are case
insensitive, e.g.::

   >>> dct = CIMultiDict(key='val')
   >>> 'Key' in dct
   True
   >>> dct['Key']
   'val'

*Keys* should be ``str`` or ``istr`` instances.

The library has optional Cython_ optimization for sake of speed.


License
-------

Apache 2


.. _aiohttp: https://github.com/KeepSafe/aiohttp
.. _Cython: http://cython.org/


Changelog
---------
See `RTD page <http://multidict.readthedocs.org/en/latest/changes.html>`_.
