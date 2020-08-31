=========
Bootstrap
=========

This is an initialization script that might be used to load things that need to be loaded en advance. It runs every time Unity loads and compiles.
It currently is used to process the SetExecutionOrder attribute.

If you want to expand it, insert your code into the static constructor. If you add it anywhere else, it is likely to not work.

****

**GET HELP**
------------

`Join this Discord server <https://discord.gg/CvG3p7Q>`_ to get help from the community, suggest new features, and vote on future updates!

.. seealso::

    * `Attributes (C#) <https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/attributes/>`_
    * :ref:`SetExecutionOrder`