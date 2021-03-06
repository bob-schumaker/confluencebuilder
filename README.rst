.. -*- restructuredtext -*-

=======================================
Atlassian Confluence Builder for Sphinx
=======================================

.. image:: https://img.shields.io/pypi/v/sphinxcontrib-confluencebuilder.svg
   :target: https://pypi.python.org/pypi/sphinxcontrib-confluencebuilder
   :alt: pip Version

.. image:: https://github.com/sphinx-contrib/confluencebuilder/workflows/build/badge.svg?branch=master
    :target: https://github.com/sphinx-contrib/confluencebuilder/actions?query=workflow%3Abuild
    :alt: Build Status

.. image:: https://readthedocs.org/projects/sphinxcontrib-confluencebuilder/badge/?version=latest
   :target: https://sphinxcontrib-confluencebuilder.readthedocs.io/
   :alt: Documentation Status

.. image:: https://img.shields.io/pypi/dm/sphinxcontrib-confluencebuilder.svg
   :target: https://pypi.python.org/pypi/sphinxcontrib-confluencebuilder/
   :alt: PyPI download month

Sphinx_ extension to build Confluence storage format files and optionally
publish them to a Confluence instance.

Requirements
============

* Python_ 2.7 or 3.5+
* Requests_ 2.14.0+
* Sphinx_ 1.8 or 2.4+

If publishing:

* Confluence_ Cloud or Server 6.13+

Installing
==========

The recommended method to installing this extension is using pip_:

.. code-block:: shell

   pip install sphinxcontrib-confluencebuilder
    (or)
   python -m pip install sphinxcontrib-confluencebuilder

For a more in-depth installation information, see also:

 | Atlassian Confluence Builder for Sphinx - Installation
 | https://sphinxcontrib-confluencebuilder.readthedocs.io/en/stable/install.html

Usage
=====

- Register the extension ``sphinxcontrib.confluencebuilder`` in the project's
  configuration script (``conf.py``):

.. code-block:: python

   extensions = ['sphinxcontrib.confluencebuilder']

- Run sphinx-build with the builder ``confluence``:

.. code-block:: shell

   sphinx-build -b confluence . _build/confluence -E -a
    (or)
   python -m sphinx -b confluence . _build/confluence -E -a

For more information on the usage of this extension, see also:

 | Atlassian Confluence Builder for Sphinx - Tutorial
 | https://sphinxcontrib-confluencebuilder.readthedocs.io/en/stable/tutorial.html

Configuration
=============

The following is an example of a simple configuration for Confluence generation
and publishing:

.. code-block:: python

   extensions = ['sphinxcontrib.confluencebuilder']
   confluence_publish = True
   confluence_space_name = 'TEST'
   confluence_parent_page = 'Documentation'
   confluence_server_url = 'https://intranet-wiki.example.com/'
   confluence_ask_user = True
   confluence_ask_password = True

For a complete list of configuration options, see also:

 | Atlassian Confluence Builder for Sphinx - Configuration
 | https://sphinxcontrib-confluencebuilder.readthedocs.io/en/stable/configuration.html

Directives
==========

For a complete list of directives supported by this extension, please consult:

 | Atlassian Confluence Builder for Sphinx - Directives
 | https://sphinxcontrib-confluencebuilder.readthedocs.io/en/stable/directives.html

Demonstration
=============

The set of example documents used to assist in validation/testing can be found
here:

 | Atlassian Confluence Builder for Sphinx - Validation Set
 | https://github.com/sphinx-contrib/confluencebuilder/tree/master/tests/validation-sets

The active and older versions of published validation documents can be found
here:

 | Atlassian Confluence Builder for Sphinx - Online Demo on Confluence Cloud
 | https://sphinxcontrib-confluencebuilder.atlassian.net/

Compatibilities
===============

For a complete list of supported markup, extensions, etc.; consult the
following:

 | Atlassian Confluence Builder for Sphinx - Compatibilities
 | https://sphinxcontrib-confluencebuilder.readthedocs.io/en/stable/compatibilities.html

.. _Confluence: https://www.atlassian.com/software/confluence
.. _Python: https://www.python.org/
.. _Requests: https://pypi.python.org/pypi/requests
.. _Sphinx: https://www.sphinx-doc.org/
.. _pip: https://pip.pypa.io/
