==========
Attributes
==========

Attributes are declarations that change script metadata, and allow for some useful features when correctly used. `Visit this page to know more about attributes <https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/attributes/>`_.

These attributes should make it easier to organize the inspector without much effort or any learning curve.
Some aren't aesthetic-related, but rather quality-of-life features that will improve workflow, reducing the amount of times you'll have to switch windows.

Overview
--------

    * :ref:`Aesthetic <**AESTHETIC**>`
        * :ref:`BigHeader`
        * :ref:`Label`
        * :ref:`Splitter`
        * :ref:`SubHeader`
    * :ref:`Functional <**FUNCTIONAL**>`
        * :ref:`SetExecutionOrder`

**AESTHETIC**
-------------

.. warning::
    These attributes override all other aesthetic attributes, no matter the order of execution. This means they are incompatible with Range and Header, and likely Tooltip, but not SerializeField, for example.

BigHeader
---------

**Affects:** Variables

Creates a big header above the target variable.

**Parameters**

.. table::
    :widths: auto

    ======   ========   ===================================================================
    Type     Name       Description
    ======   ========   ===================================================================
    string   title      *The header's title.*
    string   subtitle   *The sub-header to go underneath the header. Leave blank for none.*
    ======   ========   ===================================================================

IMAGE GOES HERE

Label
-----

**Affects:** Variables

Changes the variable's name in the inspector. It won't affect the script itself.

IMAGE GOES HERE

Splitter
--------

**Affects:** Variables

Creates a line above the target variable with custom coloring and thickness (optional).

**Parameters**

.. table::
    :widths: auto

    ======   =========   ===========================================
    Type     Name        Description
    ======   =========   ===========================================
    int      thickness   *The line's thickness. Default value is 1.*
    int      r           *The red value of the line's color.*
    int      g           *The green value of the line's color.*
    int      b           *The blue value of the line's color.*
    int      a           *The alpha value of the line's color.*
    ======   =========   ===========================================

.. table::
    :widths: auto

    ======   =========   ===================================================================
    Type     Name        Description
    ======   =========   ===================================================================
    int      thickness   *The line's thickness. Default value is 1.*
    Color    color       *The line's color.*
    ======   =========   ===================================================================

IMAGE GOES HERE

SubHeader
---------

**Affects:** Variables

Creates a smaller header above the target variable.

**Parameters**

.. table::
    :widths: auto

    ======   ========   =========================
    Type     Name       Description
    ======   ========   =========================
    string   title      *The sub-header's title.*
    ======   ========   =========================


**FUNCTIONAL**
--------------

SetExecutionOrder
-----------------

**Affects:** Classes

Sets the script's `execution order <https://docs.unity3d.com/Manual/class-MonoManager.html>`_ on the Execution Order settings for you. You only have to provide a value. A number below zero indicates the script will run before Default Time. A value greater than zero means it'll run after Default Time.

Setting it to zero is likely to change nothing.

This attribute is applied in the `IvyCoreBootstrap.cs <.\docs\pages\bootstrap>`_ file.

IMAGE GOES HERE

****

**GET HELP**
------------

`Join this Discord server <https://discord.gg/CvG3p7Q>`_ to get help, suggest new features, and vote on future updates!

.. seealso::

    * `Attributes (C#) <https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/attributes/>`_
    * `Script Execution Order <https://docs.unity3d.com/Manual/class-MonoManager.html>`_