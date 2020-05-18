==============================
IvyArrayUtils and IvyListUtils
==============================

Overview
--------

    * :ref:`Append` 
    * :ref:`Insert and RemoveAt` 
    * :ref:`MoveUp and MoveDown` 
    * :ref:`OffsetUp and OffsetDown`
    * :ref:`Get Help <**GET HELP**>` 

**UTILITIES**
-------------

Append
------

* ``Append(ref T[] array, T item)``

Adds an item to the end of the array.

.. note::
    ArrayUtils-only content.
    Equivalent to ``List.Add``.

.. code-block:: csharp
    :linenos:

    using IvyTools.Utilities;
    using UnityEngine;

    public class MyClass: MonoBehaviour
    {
        string[] array =
        {
            "Text 0", "Text 1", "Text 2",
            "Text 3", "Text 4", "Text 5"
        };

        void MyMethod()
        {
            // Array is set to
            // [ "Text 0", "Text 1", "Text 2", "Text 3", "Text 4", "Text 5", "Text 6" ]
            IvyArrayUtils.Append(ref array, "Text 6");
        }

    }

Insert and RemoveAt
-------------------

* ``Insert(ref T[] array, T item, int index)``
* ``RemoveAt(ref T[] array, int index)``

**Insert** adds an item in the specified index, and moves all items in the array one index lower, expanding the array by one.
**RemoveAt** removes the item at the specified index, moves all lower items in the array one index up, and shrinks the array.

.. note::
    ArrayUtils-only content.
    Equivalent to ``List<T>.Insert()`` and ``List<T>.RemoveAt()`` for arrays, respectively.

.. code-block:: csharp
    :linenos:

    using IvyTools.Utilities;
    using UnityEngine;

    public class MyClass: MonoBehaviour
    {
        string[] array =
        {
            "Text 0", "Text 1", "Text 2",
            "Text 3", "Text 4", "Text 5"
        };

        void MyMethod()
        {
            // Array is set to
            // [ "Text 0", "Text 1", "Text 2", "Inserted Text", "Text 3", "Text 4", "Text 5" ]
            IvyArrayUtils.Insert(ref array, "Inserted Text", 3);
            
            // Array is set to
            // [ "Text 0", "Text 1", "Text 2", "Text 3", "Text 4", "Text 5" ]
            IvyArrayUtils.RemoveAt(ref array, 3);
        }
    }

MoveUp and MoveDown
-------------------

* ``MoveUp(ref T[]/List<T> array, int index)``
* ``MoveDown(ref T[]/List<T> array, int index)``

**MoveUp** swaps the item at index with the one an index above. If index is 0, the item will be swapped with the last entry in the array. 
**MoveDown** swaps the item at index with the one an index below. If index is array.Length - 1 (the last index), the item will be swapped with the first entry in the array.

.. code-block:: csharp
    :linenos:

    using IvyTools.Utilities;
    using UnityEngine;

    public class MyClass: MonoBehaviour
    {
        string[] array =
        {
            "Text 0", "Text 1", "Text 2",
            "Text 3", "Text 4", "Text 5"
        };

        List<string> list = new List<string>()
        {
            "Text 0", "Text 1", "Text 2",
            "Text 3", "Text 4", "Text 5"
        };

        void MyMethod()
        {
            // Array is set to
            // [ "Text 0", "Text 2", "Text 1", "Text 3", "Text 4", "Text 5" ]
            IvyArrayUtils.MoveUp(ref array, 2);

            // List is set to
            // [ "Text 0", "Text 1", "Text 3", "Text 2", "Text 4", "Text 5" ]
            IvyListUtils.MoveDown(ref list, 2);
        }
    }

OffsetUp and OffsetDown
-----------------------

* ``OffsetUp(ref T[]/List<T> array, int steps)``
* ``OffsetDown(ref T[]/List<T> array, int steps)``

**OffsetUp** moves all values up on the array as many times as specified.
**OffsetDown** moves all items down on the array as many times as specified.

.. code-block:: csharp
    :linenos:

    using IvyTools;
    using UnityEngine;

    public class MyClass: MonoBehaviour
    {
        string[] array =
        {
            "Text 0", "Text 1", "Text 2",
            "Text 3", "Text 4", "Text 5"
        };

        List<string> list = new List<string>()
        {
            "Text 0", "Text 1", "Text 2",
            "Text 3", "Text 4", "Text 5"
        };

        void MyMethod()
        {
            // Array is set to
            // [ "Text 1", "Text 2", "Text 3", "Text 4", "Text 5", "Text 0" ]
            IvyArrayUtils.OffsetUp(ref array); 
    
            // List is set to
            // [ "Text 4", "Text 5", "Text 0", "Text 1", "Text 2", "Text 3" ]
            IvyListUtils.OffsetDown(ref list, 2);
        }
    }

****

**GET HELP**
------------

`Join this Discord server <https://discord.gg/CvG3p7Q>`_ to get help, suggest new features, and vote on future updates!

.. seealso::

    * `Collections <https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/collections>`_
    * `LINQ <https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/linq/>`_
    * `Arrays <https://docs.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/arrays>`_
    * `System.Array <https://docs.microsoft.com/en-us/dotnet/api/system.array?view=netcore-3.1>`_

    * :ref:`IvyColorUtils <colorutils>`
    * :ref:`IvyIOUtils <ioutils>`
    * :ref:`IvyLogUtils <logutils>`
    * :ref:`IvyTextureUtils <textureutils>`