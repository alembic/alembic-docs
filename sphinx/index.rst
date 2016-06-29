.. rubric:: Alembic |version|

Alembic is an open source geometry caching format that promotes interoperability
between authoring tools. From `alembic.io <http://alembic.io>`_:

    *Alembic distills complex, animated scenes into a non-procedural, application-
    independent set of baked geometric results. This ‘distillation' of scenes into 
    baked geometry is exactly analogous to the distillation of lighting and rendering 
    scenes into rendered image data.*

Alembic is focused on efficiently storing the computed results of complex procedural 
geometric constructions. It is specifically NOT concerned with storing the complex 
dependency graph of procedural tools used to create the computed results. For example, 
Alembic will efficiently store the animated vertex positions and animated transforms 
that result from an arbitrarily complex animation and simulation process, but will not
attempt to store a representation of the network of computations (rigs, basically) which
were required to produce the final, animated vertex positions and animated transforms.


Get Alembic
-----------

The Alembic code can be found in a git repository at ::

    $ git clone http://github.com/alembic/alembic


Build Alembic
-------------

Before Alembic can be built, you will need to satisfy its external
dependencies:

Required:

    - A unix-like OS (Linux, Mac OS X); Windows support is experimental
    - `CMake (2.8.11) <http://www.cmake.org>`_
    - `ilmbase (1.0.3) <http://www.openexr.com>`_

Optional:

    - `HDF5 (1.8.9) <http://www.hdfgroup.org/HDF5>`_
    - `Boost (1.44) <http://www.boost.org>`_
    - pyilmbase (1.0.3)
    - Arnold (3.0)
    - Pixar PRMan (15.x)
    - Autodesk Maya (2012)


Note that the versions given parenthetically above are minimum-tested
versions.  You may have good luck with later or earlier versions, but this is
what we've been building Alembic against.

Run the cmake command. You can either run this in your source root, or
create a separate build root and pass the source root to cmake: ::

    $ cd <source root>
    $ cmake [OPTIONS]

Some of the available build options can be found in the 
`CMakeLists.txt <https://github.com/alembic/alembic/blob/master/CMakeLists.txt#L63>`_ file.


API Reference
-------------

Click here for the C++ API reference documentation:

    :ref:`API Reference <alembic-intro>` 


PyAlembic
---------

In order to use Alembic in Python, you must first build both Alembic and the Alembic 
Python bindings. ::

    $ cmake -DUSE_PYALEMBIC

The Alembic Python bindings have been tested with 
`Python 2.6 <http://www.python.org/download/releases/2.6.8/>`_, 
and require `PyImath <http://github.com/openexr/openexr>`_ and 
`Boost::Python <http://boost.org>`_ libraries to run. 

The :ref:`Introduction to PyAlembic <pyalembic-intro>` document is intended to serve
as a brief introduction and  programmer's guide to using the Alembic Python bindings. 
You can also search the :ref:`Python Module Index <modindex>`. 


Help
----

If you get stuck, contact us on the alembic-discussion mailing list. You can
view the mailing list archives and join the mailing list via

http://groups.google.com/group/alembic-discussion


