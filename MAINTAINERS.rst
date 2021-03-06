Maintainers
===========

This document serves as a reminder/guide for maintainers for this extension. For
users wishes to contribute to this extension, please consult `CONTRIBUTING.rst`_
instead.

System testing
--------------

When a major release is made, it is recommended to perform system testing on all
supported versions of Confluence Server and Confluence Cloud. Test both
Confluence Cloud with an organization account and a user account (tilde-leading)
as well as all Confluence supported server revisions (consult
`Atlassian Support End of Life Policy`_ for the most recent list).

Release steps
-------------

When implementation is deemed to be ready for a stable release, ensure the
following steps are performed:

- Ensure newly added/changed configuration options are properly reflecting a
  ``versionadded`` or equivalent hint.
- Update ``CHANGES.rst``, replacing the development title with release version
  and date.
- Ensure version values in the implementation are incremented and tagged
  appropriately. The tagged commit should have a "clean" version string.
- Ensure the release tag is signed.
- After invoking ``bdist_wheel``, ensure a universal wheel has been created
  (i.e. inspect that the generated package inside ``dist/``  properly reflects
  ``py2.py3`` support).

A release can be made with the following commands:

.. code-block:: shell-session

    $ python setup.py clean --all
    running clean
    ...
    $ python setup.py sdist bdist_wheel
    running sdist
    running egg_info
    ...
    $ twine upload dist/*

Sanity checks and cleanup
-------------------------

After a release has been published to PyPI and a tag is available for users to
reference, ensure the following post-release tasks are performed:

- Verify Read the Docs space reflects the most recent documentation. ``stable``
  should now point to the most recent release. The contents of ``latest`` should
  match the ``stable`` documentation. Also, ensure the newly created tag is
  listed as a valid option for users to reference.
- Generate online validation set (examples) based off the recent release tag.
  This includes both the version space and the ``STABLE`` space. Overrides for
  consideration:

  .. code-block:: python

      # version space
      config_overrides['confluence_space_name'] = 'V010X00'
      config_test_key = 'v1.x'
      config_test_desc = 'v1.x release'

      # stable space
      config_overrides['confluence_space_name'] = 'STABLE'
      config_test_key = 'Stable'
      config_test_desc = 'stable release (v1.x)'

.. _Atlassian Support End of Life Policy: https://confluence.atlassian.com/support/atlassian-support-end-of-life-policy-201851003.html
.. _CONTRIBUTING.rst: https://github.com/sphinx-contrib/confluencebuilder/blob/master/CONTRIBUTING.rst
