============
Installation
============

Dependencies
------------

`Python`_ 3.7 or later is required. `Anaconda Distribution`_ is
recommended for new starters, it includes Python and few useful packages
including a package management tool pip (see below).

`pip`_ is a package management system for installing and updating Python
packages. pip comes with Python, so you get pip simply by installing
Python. On Ubuntu and Fedora Linux, you can simply use your system
package manager to install the ``python3-pip`` package. `The
Hitchhiker’s Guide to Python`_ provides some guidance on how to install
Python on your system if it isn’t already; you can also install Python
directly from `python.org`_. You might want to `upgrade pip`_ before
using it to install other programs.

Install via ``pip``
-------------------

1. to use ``pip`` install from PyPI:

   .. code:: sh

      pip install --upgrade sfeprapy

2. or get the most developemnt version (requires `git`_):

   =Note installing ``SfePrapy`` via this route will include the lastest
   commits/changes to the library.=

   .. code:: sh

      pip install --upgrade "git+https://github.com/fsepy/SfePrapy.git@dev"

Install local
-------------

todo

Test installation
-----------------

``sfeprapy`` command line interface (CLI) uses the current working
directory to obtain and/or save files.

To get help
~~~~~~~~~~~

.. code:: sh

   sfeprapy -h

To produce a ``sfeprapy.mcs0`` example input file
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code:: sh

   sfeprapy mcs0 template example_input.csv

To run ``sfeprapy.mcs0`` simulation
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code:: sh

   sfeprapy mcs0 -p 4 example_input.csv

``sfeprapy.mcs0`` uses the `multiprocessing`_ library to utilise full
potential performance of multi-core CPUs. The ``-p 4`` defines 4 threads
will be used in running the simulation, 1 is the default value.

.. _Python: https://www.python.org/downloads/
.. _Anaconda Distribution: https://www.anaconda.com/distribution/#download-section
.. _pip: https://pypi.org/
.. _The Hitchhiker’s Guide to Python: https://docs.python-guide.org/starting/installation/
.. _python.org: https://www.python.org/getit/
.. _upgrade pip: https://pip.pypa.io/en/stable/installing/
.. _git: https://git-scm.com/downloads
.. _multiprocessing: https://docs.python.org/3.4/library/multiprocessing.html#module-multiprocessing
