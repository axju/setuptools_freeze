=================
setuptools_freeze
=================
Integrate "pyinstaller" to "setuptools". This will make it easy to freeze your
package. More precisely, it will create a executable file form the console
scripts entry points in your package.


How to use
----------
Add "setuptools_freeze" to your setup requires::

  setup(
      ...
      setup_requires=[
          'setuptools_freeze',
          ...
      ],
      entry_points={
          'console_scripts': ['<script name>=mypackage.gui:main']
      },
      ...
  )

Now you can freeze your project::

  python setup.py pyinstaller

This will create the folder "dist/<script name>", which include the executable
file.

If you also use "Inno Setup" to create a executable setup file, you can use the
"inno" command. Before that you have to do two thinks.
1. Install "Inno Setup" and add the compiler to your $PATH
2. Add a guid to the setup file
Now you can run::

  python setup.py inno

Developer nodes
---------------
This is still under develop. This is even more a proof of concept, than a
beautiful package. But it work for my case and hopefully I will make it
beautiful in future.

Developer tools::

  python -m pip install --upgrade pip wheel setuptools flake8 tox

Install::

  python setup.py install

Test::

  python setup.py flake8
  python setup.py test

Build::

  python setup.py build

ToDo
----
1. create build folder if not exist
