===============================
Sphinx + Read The Docs + Github
===============================

Having deployed my tutorials in `Read the Docs <https://readthedocs.org/>`_, my first tutorial is going to be how to install the tools necessary for authoring and deploying these tutorial.

.. note::

	Currently, there is **no installer** available for Windows. You need to use the Python package manager **PIP** to install Sphinx.

1. Install Python

- Download `Python 3.x <https://www.python.org/downloads/>`_ and run the installer.
- Install Python to the default location.
- Add the Python executable folder to the system path (At the end of installation, Select the optional checkbox to automatically add the Python folder to the system path)

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

Now, the file structure would be,

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

The above file indicates that there are two sub-pages ``sphinx-setup.rst`` & ``avr-programmer.rst`` and are located inside the ``contents`` folder.

5. Preview the HTML Page

- Run the following command inside the ``docs`` folder

.. code-block:: bash

	sphinx-build -b html . build
	
This generates the HTML files inside the ``build`` folder. You can open the ``index.html`` page to preview your webpage.

6. Install git

git is an open source distributed version control system that can track the history of computer files. `GitHub <https://github.com/>`_ is an online web service that hosts git repositories and supports colloborative development.

- Download `git <https://git-scm.com/downloads>`_ and install to the default location.

7. Configure git

- Navigate to ``MyTutorials`` folder, right click and select ``git bash here``.
- Type the following commands to configure git

.. code-block:: shell

	git config --global user.name "Your name" user.email "Your email"
	
The above configuration needs to be done only once in your PC.

- Run the following command to initialize a local repository inside your MyProjects folder.

.. code-block:: shell

	git init

- Stage and commit the files

.. code-block:: shell

	git add .
	git commit -m "Initial commit"
	
8. Upload to github.com (`Detailed steps <https://help.github.com/en/github/importing-your-projects-to-github/adding-an-existing-project-to-github-using-the-command-line>`_)

- Create a account in `GitHub <https://github.com/>`_
- Create a new repository in github.
- Execute the following commands from the git command line

.. code-block:: shell

	git remote add origin https://github.com/your-github-username/your-repo-name
	git push -u origin master
	
The above command uploads your changes to the online repository github.

9. Link your github repo to readthedocs

- Create a account in `Read the Docs <https://readthedocs.org/>`_ and link your github account.
- This shows all your github projects.
- Select the project and build.
- Once build is successful, the online site is available as projectname.readthedocs.io

