.. _youtube-dl:     https://ytdl-org.github.io/youtube-dl/index.html
.. _opensource:		https://github.com/ytdl-org/youtube-dl
.. _FFmpeg:			https://www.ffmpeg.org/download.html

=======================
Download youtube videos
=======================

`youtube-dl`_ is a `opensource`_ command line utility to help download youtube videos in various formats.

Installation
############

The executable can be directly downloaded from https://youtube-dl.org/downloads/latest/youtube-dl.exe. However, you need to manually download the youtube-dl executable, everytime, you want to update it. The elegant solution is to install and update the utility from Python command line using the PIP installer.

1. Install Python

- Download `Python 3.x <https://www.python.org/downloads/>`_ and run the installer.

- Install Python to the default location.

- Add the Python executable folder to the system path (At the end of installation, Select the optional checkbox to automatically add the Python folder to the system path)

2. Install youtube-dl

- Once the path is added to the command line the following commands can be executed from the command line.

.. code-block:: bash

	pip install youtube-dl
	pip install --upgrade youtube-dl

3. Install `FFmpeg`_ 

You can merge the video and audio of two formats into a single file using ``-f <video-format>+<audio-format>``. This requires ffmpeg software.

- Download the static library from https://ffmpeg.zeranoe.com/builds/

- Place the extracted contents in a folder.

- `Set your PATH environment variable <https://www.java.com/en/download/help/path.xml>`_ to point to the directory in which the ffmeg.exe is located.

Commands
########

- Display Version

.. code-block:: bash

	youtube-dl --version

- Display help

.. code-block:: bash

	youtube-dl --help

- Display available video formats

.. code-block:: bash

	youtube-dl -F youtube-link
	
- Extract only audio and store in ``D:/youtube`` folder

.. code-block:: bash

	youtube-dl --extract-audio --audio-format mp3 -c -o "D:/youtube/%(title)s.%(ext)s" youtube-link

- Download 720p video 

.. code-block:: bash

	youtube-dl -v -f 22 -c -o "D:/youtube/%(title)s.%(ext)s" youtube-link

- Download 720p video or best available format 

.. code-block:: bash

	youtube-dl -v -f 22/bestvideo[ext=mp4]+bestaudio[ext=m4a] -c -o "D:/youtube/%(title)s.%(ext)s" youtube-link

- Download 1080p or 720p video or best available format 

.. code-block:: bash

	youtube-dl -v -f 137+140/22/bestvideo[ext=mp4]+bestaudio[ext=m4a] -c -o "G:/youtube/%(title)s.%(ext)s" 

- Generate a list of files available in a playlist

.. code-block:: bash

	youtube-dl -s --skip-download -o "%(playlist_index)03d %(title)s.%(ext)s" --get-filename  youtube-link > "D:\youtube\fileslist.txt"

- Download videos from a playlist

.. code-block:: bash

	youtube-dl -v -f 22/bestvideo[ext=mp4]+bestaudio[ext=m4a] -c -o "D:/youtube/%(playlist)s/%(playlist_index)02d %(title)s.%(ext)s" --playlist-start 1 --playlist-end 5  youtube-link
	
- Download videos from URLs mentioned in ``D:/youtube/fileslist.txt``

.. code-block:: bash

	youtube-dl -v -f 22/bestvideo[ext=mp4]+bestaudio[ext=m4a] -c -o "D:/youtube/%(autonumber)02d %(title)s.%(ext)s" --autonumber-start 1 --batch-file "D:/youtube/fileslist.txt"

