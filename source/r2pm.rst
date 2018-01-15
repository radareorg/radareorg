:orphan:

.. _r2pm:

r2pm
=====

Radare2 comes with its own package manager, ``r2pm``;
its packages/plugins are on `github <https://github.com/radare/radare2-pm>`__.

To start using it, you need to initialize the database:

::

  $ r2pm init

You can refresh it at any time:

::

  $ r2pm update

You can get a complete list of every packages:

::

  $ r2pm -s

Installing a package is easy:

::

  $ r2pm install [package name]
