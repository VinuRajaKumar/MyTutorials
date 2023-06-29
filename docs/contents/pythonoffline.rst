Python packages offline installation (Windows)
==============================================
Lets say, we have two PCs with identical software configuration (OS, number of bits & python version); **Internet PC**, the one that has access to internet and a **Target PC**, which has no access to interet. The following steps describe how to update/install python packages in the **Target PC** with the help of **Internet PC**.

1. Open command prompt and enter the following commands. [**Internet PC**]
 
 .. code-block:: bash
 
	pip download package-name -d ./package-dir
	
The above command downloads the requested package along with its dependencies to the package-dir. 

2. Transfer the package-dir to the PC that has **no access to the internet**.

3. Execute the following commands in the command prompt. [**Target PC**]

Installation
 .. code-block:: bash
 
	pip install --no-index --find-links=./package-dir package-name

Update
 .. code-block:: bash
 
	pip install -U --no-index --find-links=./package-dir package-name
	
This installs the package and its dependencies in the target machine.

Example

Installation
 .. code-block:: bash
 
	pip download sphinx -d "H:/pythonoffline/Sphinx"
	pip install --no-index --find-links="H:/pythonoffline/Sphinx" Sphinx

Update
 .. code-block:: bash
 
	pip download sphinx -d "H:/pythonoffline/pip"
	pip install -U --no-index --find-links="H:/pythonoffline/pip" pip


[1] https://superuser.com/questions/1523218/how-to-install-python-packages-with-all-dependencies-offline-via-pip3