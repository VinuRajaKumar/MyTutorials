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

2. Install Sphinx `[Link] <http://www.sphinx-doc.org/en/master/usage/installation.html#windows>`_

- Open Command Prompt and type,

.. code-block:: bash

	pip install -U sphinx

3. Install **Read the Docs Sphinx** theme

.. code-block:: bash

	pip install -U sphinx_rtd_theme	

4. Configure Sphinx

- If you want to host your pages in github and expect `Read the Docs <https://readthedocs.org/>`_ to automatically build your pages, then all your project documents (\*.rst) should reside inside a folder ``docs``.
- Minimum files required under the "docs" folder are : ``conf.py`` and ``index.rst``. Actually, the index.rst file can be in any other name. For example it can be ``contents.rst`` also.
	
- Download and extract the template folder from `Template <https://github.com/readthedocs/>`_.
	
- Copy and paste the ``conf.py`` and ``index.rst`` files under your docs folder.

- Open ``conf.py`` and add/modify the following lines

.. code:: python

	# Import the theme
	import sphinx_rtd_theme

	# The master toctree document.
	# Specify the root file of your documentation
	# without extension (.rst).
	master_doc = 'index'

	# General information about the project.
	project = u'My Tutorials'
	copyright = u'2020, Vinu Raja Kumar C'

	# Add the python extension
	extensions = [
		...
		'sphinx_rtd_theme',
	]
	
	# Specify the theme for the HTML pages
	html_theme = "sphinx_rtd_theme"

- Create a folder ``contents`` inside ``docs`` folder and place the sub-pages. ( ``page1.rst`` & ``page2.rst``).

Now, he file structure would be,

	| MyTutorials/
	| └--- docs/         
	|        ├─ conf.py
	|        ├─ index.rst
	|        └─ contents/
	|                  ├--- page1.rst
	|                  └--- page2.rst

- The index.rst is like a table of contents page.

.. code:: rst

	.. My Tutorials documentation master file, created by
	sphinx-quickstart on Sat Apr  4 12:23:59 2020. You can
	adapt this file completely to your liking, but it should 
	at least contain the root `toctree` directive.

	Welcome to My Tutorials!
	=======================================
	I had been looking for ways to archive and look back the things that I have
	learned over the years. Recently, I came across this document hosting site `Read
	the Docs <https://readthedocs.org/>`_ and a document generation tool `SPHINX 
	<https://www.sphinx-doc.org/en/master/>`_. The `Read the Docs <
	https://readthedocs.org/>`_ site can host the documentation directly from version 
	control repository service `GitHub <https://github.com/>`_. The `SPHINX <
	https://www.sphinx-doc.org/en/master/>`_ tool allows us to write the documentation 
	in a markup language called `reStructuredText <
	http://docutils.sourceforge.net/rst.html>`_. This tutorial has been completly 
	written using these tools and has been hosted in the online repository github.

	.. toctree::
	   :numbered: 1
	   :maxdepth: 1
	   :titlesonly:
	   :caption: Contents
	   :name: TOC

	   contents/sphinx-setup
	   contents/avr-programmer

5. Preview the HTML Page

- Run the following command inside the docs folder

.. code-block:: bash

	sphinx-build -b html . build
	
This generates the HTML files inside build folder.

	