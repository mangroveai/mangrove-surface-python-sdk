===========================
Mangrove Surface Python SDK
===========================

.. image:: https://circleci.com/gh/mangroveai/mangrove-surface-python-sdk.svg?style=svg
    :target: https://circleci.com/gh/mangroveai/mangrove-surface-python-sdk

.. image:: https://readthedocs.org/projects/mangrove-surface-python-sdk/badge/?version=stable
    :target: https://mangrove-surface-python-sdk.readthedocs.io/en/latest/?badge=stable
    :alt: Documentation Status

.. _documentation: http://mangrove-surface-python-sdk.readthedocs.io/

Documentation
-------------

A complete documentation is available there: documentation_

Installation
------------

Install the python SDK package:

.. code-block:: python

    pip install mangrove-surface

or using the git repository::

    git clone https://github.com/mangroveai/mangrove-surface-python-sdk
    python setup.py install

(*optional*) Setup your environment variables
---------------------------------------------

You can used the SDK with an explicit configuration of url instance and token
or you can provide them as environment variables: ``SURFACE_URL`` and
``SURFACE_TOKEN``.

For example on unix-like system:

.. code-block:: shell

    $ export SURFACE_URL=http://your_mangrove.ai_url/api
    $ export SURFACE_TOKEN='eyJ0eXAiOiJKV1QiLCJhbGciOiJ...'

.. warning:: Mangrove Surface URL have to end with ``/api``.

.. note:: The explicit configuration overrides the implicit one.

.. note:: Token can be provided by the administrator using GUI (see
  documentation) or using the SDK (see
  :meth:`mangrove.Surface._Admin.create_token`:)


Test your installation
----------------------

You can run tests with the following python lines:

 - Test if it is properly installed:

.. code-block:: python

    >>> import mangrove_surface
    >>> mangrove_surface.__version__
    '2.0.0'

The python SDK is properly connected to your Mangrove Surface:

.. code-block:: python

    >>> from mangrove_surface import SurfaceClient
    >>> # if environment variables are setup
    >>> client = SurfaceClient()
    >>> # otherwise
    >>> # client = SurfaceClient(url="...", token="...")
    >>> client.admin.versions()
    [
        {
            'name': 'atlas',
            'version': '1.0.0'
        }, {
            'name': 'license_authority',
            'version': u'1.5.0'
        }, {
            'name': 'dmgr',
            'version': '1.0.0'
        }, {
            'name': 'modeler',
            'version': '1.0.0'
        }, {
            'name': 'exporter',
            'version': '1.0.0'
        }, {
            'name': 'mangrove-surface-sdk',
            'version': '1.0.0'
        }
    ]

It is well configured! Congratulation!

Let's begin with :doc:`surface`.

Support
-------

Please refer to :doc:`logger` section if you have any unexpected behavior using
the SDK.
