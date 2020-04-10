============================
Sphinx + Read The Docs Setup
============================

Having deployed my tutorials in `Read the Docs <https://readthedocs.org/>`_, my first tutorial is going to be how to install the tools necessary for authoring and deploying these tutorial.

.. note::

	Currently, There are no installers available for Windows. We need to use the Python package manager **PIP** to install Sphinx.

1. Install Python

  - Download Python 3.x from here https://www.python.org/downloads/
  - Run the executable, install to the default location.
  - Add the Python executable folder to the system path (Select the checkbox to automatically add by the installer)

2. Install Sphinx

  - Open Command Prompt and type, Ref : http://www.sphinx-doc.org/en/master/usage/installation.html#windows

.. code-block:: bash

	C:\> pip install -U sphinx

3. Setup Sphinx
 
The software comes with a sphinx-quickstart script that sets up a source directory and creates a default conf.py with the most useful configuration values from a few questions it asks you. I have created a folder **D:/Sphinx/Documentation** to hold all the documentation. To use this, run:

.. code-block:: bash

	D:/Sphinx/Documentation>sphinx-quickstart

4. Add the theme in config.py

5. Add contents to the files

6. Run the following command to generate HTML files.

.. code-block:: bash

	D:/Sphinx/Documentation>sphinx-build -b html sourcedir builddir

	