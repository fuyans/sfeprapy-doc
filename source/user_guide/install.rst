============
Installation
============

Dependencies
------------

`Python`_ 3.7 or later is required. `Anaconda Distribution`_ is
recommended for new starters. It automatically setup some useful tools 
(e.g. `pip`_, virtual environment manager etc).

``pip`` install
---------------

*click* `pip`_ *to learn more*.

1. to use ``pip`` install from PyPI:

   .. code:: sh

      pip install --upgrade sfeprapy

2. or get the most recent version under developemnt from ``GitHub`` (requires `git`_):

   .. code:: sh

      pip install --upgrade "git+https://github.com/fsepy/sfeprapy.git@dev"

Local install
-------------

`Clone`_ or download (`master`_, `dev`_) ``sfeprapy`` source code from GitHub, unzip and ``cd`` to the source code directory then install using ``pip``:

.. code:: sh

   pip install .

Test installation
-----------------

Upon successful installation of ``sfeprapy``, enter Python and check whether ``sfeprapy`` is installed properly:

.. code-block:: python

   import sfeprapy
   print(sfeprapy.__version__)
   0.8.1

.. _Python: https://www.python.org/downloads/
.. _Anaconda Distribution: https://www.anaconda.com/distribution/#download-section
.. _pip: https://pypi.org/
.. _The Hitchhiker’s Guide to Python: https://docs.python-guide.org/starting/installation/
.. _python.org: https://www.python.org/getit/
.. _upgrade pip: https://pip.pypa.io/en/stable/installing/
.. _git: https://git-scm.com/downloads
.. _Clone: https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/cloning-a-repository
.. _master: https://github.com/fsepy/SFEPRAPY/archive/refs/heads/master.zip
.. _dev: https://github.com/fsepy/SFEPRAPY/archive/refs/heads/dev.zip
