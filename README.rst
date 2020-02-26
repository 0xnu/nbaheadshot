NBA Headshots
=============
A simple package for download headshots of NBA players. It offers a premium headshots that feature a higher resolution and transparent background.

Installing
----------
You can install the package by running the command below in terminal:

.. code-block:: bash

	pip install nbaheadshot

Usage
-----
An example of a python code:

.. code-block:: python

	#!/usr/bin/env python
	#Filename: test.py
	import os
	import shutil
	import nbaheadshot

	# define the name of the directory to be created
	path = "players"

	try:
	    os.mkdir(path)
	except OSError:
	    print ("Creation of the directory %s failed" % path)
	else:
	    print ("Successfully created the directory %s " % path)

	def moveto(dst):
	    return lambda src: shutil.move(src, dst)

	action = {
	    'jpg': moveto(path),
	    'png': moveto(path),
	}

	src_dir = './'
	for file in os.listdir(src_dir):
	    ext = os.path.splitext(file)[1][1:]
	    if ext in action:
	        action[ext](os.path.join(src_dir, file))
	        print('Done!')


Make sure you have these two files `players.txt`_ and `missing_players.txt`_ in the same directory as the script. Also, create a folder called `players` then run:

.. _players.txt: https://gist.github.com/0xnu/b4826001e06570da4eee1fbf6c565c51#file-players-txt
.. _missing_players.txt: https://gist.github.com/0xnu/b4826001e06570da4eee1fbf6c565c51#file-missing_players-txt

.. code-block:: bash

	python3 test.py

License
-------
License stuff is `here`_.

.. _here: https://gist.github.com/0xnu/d11da49c85eeb7272517a9010bbdf1ab